# IsRegistryRead

- ea: `0x180085944`
- end: `0x180085b13`
- name: `IsRegistryRead`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18007cf04`

## callees

- `0x180005bfc`
- `0x180085354`
- `0x180085944`
- `0x18008d214`
- `0x18008e0f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180085981`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180085aaf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180085981`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180085aaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085a5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085adc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085a5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085adc`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180085ac8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180085af7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180085ac8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180085af7`

## string_xrefs

- `0x180085977`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x180085a14`: `RegRead`

## pseudocode

```c
__int64 __fastcall IsRegistryRead(HKEY *a1)
{
  unsigned int v2; // eax
  int v3; // eax
  int v4; // edi
  LSTATUS v5; // ebx
  unsigned int v6; // eax
  __int64 result; // rax
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  LPCSTR lpSubKey; // [rsp+68h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF
  HKEY v11; // [rsp+78h] [rbp+38h]

  hKey = 0;
  LODWORD(lpSubKey) = 1;
  v2 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config", 0, 0x20219u, &hKey);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 31, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v2);
    }
LABEL_6:
    hKey = *a1;
    v11 = 0;
    phkResult = 0;
    lpSubKey = 0;
    v3 = ConvertToNonHidden(&hKey);
    v4 = v3;
    if ( !v3 || v3 == 235 )
    {
      v5 = RegistryPathConverter((LPCWCH)hKey);
      if ( !v5 )
      {
        v5 = RegOpenKeyExA(v11, lpSubKey, 0, 0x20219u, &phkResult);
        if ( lpSubKey )
          GlobalFree((HGLOBAL)lpSubKey);
        if ( !v5 )
          RegCloseKey(phkResult);
      }
      if ( !v4 )
      {
        if ( hKey )
          GlobalFree(hKey);
      }
    }
    else
    {
      v5 = (int)lpSubKey;
    }
    return v5 == 0;
  }
  v6 = RegReadFlag(hKey, "RegRead", &lpSubKey, 0);
  if ( v6
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 32, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v6);
  }
  RegCloseKey(hKey);
  result = (unsigned int)lpSubKey;
  if ( (_DWORD)lpSubKey )
    goto LABEL_6;
  return result;
}

```

## disassembly

```asm
0x180085944  push    rbp
0x180085946  push    rbx
0x180085947  push    rdi
0x180085948  mov     rbp, rsp
0x18008594b  sub     rsp, 40h
0x18008594f  mov     rbx, rcx
0x180085952  mov     [rbp+hKey], 0
0x18008595a  lea     rax, [rbp+hKey]
0x18008595e  mov     dword ptr [rbp+lpSubKey], 1
0x180085965  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008596c  mov     [rsp+40h+phkResult], rax; phkResult
0x180085971  mov     r9d, 20219h; samDesired
0x180085977  lea     rdx, aSystemCurrentc_8; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18008597e  xor     r8d, r8d; ulOptions
0x180085981  call    cs:__imp_RegOpenKeyExA
0x180085988  nop     dword ptr [rax+rax+00h]
0x18008598d  test    eax, eax
0x18008598f  jz      short loc_180085A09
0x180085991  mov     rcx, cs:WPP_GLOBAL_Control
0x180085998  lea     rdx, WPP_GLOBAL_Control
0x18008599f  cmp     rcx, rdx
0x1800859a2  jz      short loc_1800859C8
0x1800859a4  test    byte ptr [rcx+1Ch], 80h
0x1800859a8  jz      short loc_1800859C8
0x1800859aa  cmp     byte ptr [rcx+19h], 2
0x1800859ae  jb      short loc_1800859C8
0x1800859b0  mov     rcx, [rcx+10h]
0x1800859b4  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800859bb  mov     edx, 1Fh
0x1800859c0  mov     r9d, eax
0x1800859c3  call    WPP_SF_d
0x1800859c8  mov     rax, [rbx]
0x1800859cb  lea     rcx, [rbp+hKey]
0x1800859cf  mov     [rbp+hKey], rax
0x1800859d3  mov     [rbp+arg_18], 0
0x1800859db  mov     [rbp+var_10], 0
0x1800859e3  mov     [rbp+lpSubKey], 0
0x1800859eb  call    ConvertToNonHidden
0x1800859f0  mov     edi, eax
0x1800859f2  test    eax, eax
0x1800859f4  jz      loc_180085A7B
0x1800859fa  cmp     eax, 0EBh
0x1800859ff  jz      short loc_180085A7B
0x180085a01  mov     ebx, dword ptr [rbp+lpSubKey]
0x180085a04  jmp     loc_180085B03
0x180085a09  mov     rcx, [rbp+hKey]
0x180085a0d  lea     r8, [rbp+lpSubKey]
0x180085a11  xor     r9d, r9d
0x180085a14  lea     rdx, aRegread; "RegRead"
0x180085a1b  call    RegReadFlag
0x180085a20  test    eax, eax
0x180085a22  jz      short loc_180085A5B
0x180085a24  mov     rcx, cs:WPP_GLOBAL_Control
0x180085a2b  lea     rdx, WPP_GLOBAL_Control
0x180085a32  cmp     rcx, rdx
0x180085a35  jz      short loc_180085A5B
0x180085a37  test    byte ptr [rcx+1Ch], 80h
0x180085a3b  jz      short loc_180085A5B
0x180085a3d  cmp     byte ptr [rcx+19h], 2
0x180085a41  jb      short loc_180085A5B
0x180085a43  mov     rcx, [rcx+10h]
0x180085a47  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x180085a4e  mov     edx, 20h ; ' '
0x180085a53  mov     r9d, eax
0x180085a56  call    WPP_SF_d
0x180085a5b  mov     rcx, [rbp+hKey]; hKey
0x180085a5f  call    cs:__imp_RegCloseKey
0x180085a66  nop     dword ptr [rax+rax+00h]
0x180085a6b  mov     eax, dword ptr [rbp+lpSubKey]
0x180085a6e  test    eax, eax
0x180085a70  jnz     loc_1800859C8
0x180085a76  jmp     loc_180085B0A
0x180085a7b  mov     rcx, [rbp+hKey]; lpWideCharStr
0x180085a7f  lea     r9, [rbp+lpSubKey]
0x180085a83  lea     r8, [rbp+arg_18]
0x180085a87  mov     rdx, rbx
0x180085a8a  call    RegistryPathConverter
0x180085a8f  mov     ebx, eax
0x180085a91  test    eax, eax
0x180085a93  jnz     short loc_180085AE8
0x180085a95  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180085a99  lea     rax, [rbp+var_10]
0x180085a9d  mov     rcx, [rbp+arg_18]; hKey
0x180085aa1  mov     r9d, 20219h; samDesired
0x180085aa7  xor     r8d, r8d; ulOptions
0x180085aaa  mov     [rsp+40h+phkResult], rax; phkResult
0x180085aaf  call    cs:__imp_RegOpenKeyExA
0x180085ab6  nop     dword ptr [rax+rax+00h]
0x180085abb  cmp     [rbp+lpSubKey], 0
0x180085ac0  mov     ebx, eax
0x180085ac2  jz      short loc_180085AD4
0x180085ac4  mov     rcx, [rbp+lpSubKey]; hMem
0x180085ac8  call    cs:__imp_GlobalFree
0x180085acf  nop     dword ptr [rax+rax+00h]
0x180085ad4  test    ebx, ebx
0x180085ad6  jnz     short loc_180085AE8
0x180085ad8  mov     rcx, [rbp+var_10]; hKey
0x180085adc  call    cs:__imp_RegCloseKey
0x180085ae3  nop     dword ptr [rax+rax+00h]
0x180085ae8  test    edi, edi
0x180085aea  jnz     short loc_180085B03
0x180085aec  cmp     [rbp+hKey], 0
0x180085af1  jz      short loc_180085B03
0x180085af3  mov     rcx, [rbp+hKey]; hMem
0x180085af7  call    cs:__imp_GlobalFree
0x180085afe  nop     dword ptr [rax+rax+00h]
0x180085b03  xor     eax, eax
0x180085b05  test    ebx, ebx
0x180085b07  setz    al
0x180085b0a  add     rsp, 40h
0x180085b0e  pop     rdi
0x180085b0f  pop     rbx
0x180085b10  pop     rbp
0x180085b11  retn
```
