# IsRegistryRead

- ea: `0x180081634`
- end: `0x1800817d7`
- name: `IsRegistryRead`
- size: `419`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800791fc`

## callees

- `0x180005e34`
- `0x1800810c4`
- `0x180081634`
- `0x180088d0c`
- `0x180089b70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180081671`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18008178c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180081671`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18008178c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081745`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800817ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081745`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800817ad`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008179f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800817c2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008179f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800817c2`

## string_xrefs

- `0x180081667`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800816fa`: `RegRead`

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
0x180081634  push    rbp
0x180081636  push    rbx
0x180081637  push    rdi
0x180081638  mov     rbp, rsp
0x18008163b  sub     rsp, 40h
0x18008163f  mov     rbx, rcx
0x180081642  mov     [rbp+hKey], 0
0x18008164a  lea     rax, [rbp+hKey]
0x18008164e  mov     dword ptr [rbp+lpSubKey], 1
0x180081655  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008165c  mov     [rsp+40h+phkResult], rax; phkResult
0x180081661  mov     r9d, 20219h; samDesired
0x180081667  lea     rdx, aSystemCurrentc_8; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18008166e  xor     r8d, r8d; ulOptions
0x180081671  call    cs:__imp_RegOpenKeyExA
0x180081677  test    eax, eax
0x180081679  jz      short loc_1800816EF
0x18008167b  mov     rcx, cs:WPP_GLOBAL_Control
0x180081682  lea     rdx, WPP_GLOBAL_Control
0x180081689  cmp     rcx, rdx
0x18008168c  jz      short loc_1800816B2
0x18008168e  test    byte ptr [rcx+1Ch], 80h
0x180081692  jz      short loc_1800816B2
0x180081694  cmp     byte ptr [rcx+19h], 2
0x180081698  jb      short loc_1800816B2
0x18008169a  mov     rcx, [rcx+10h]
0x18008169e  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800816a5  mov     edx, 1Fh
0x1800816aa  mov     r9d, eax
0x1800816ad  call    WPP_SF_d
0x1800816b2  mov     rax, [rbx]
0x1800816b5  lea     rcx, [rbp+hKey]
0x1800816b9  mov     [rbp+hKey], rax
0x1800816bd  mov     [rbp+arg_18], 0
0x1800816c5  mov     [rbp+var_10], 0
0x1800816cd  mov     [rbp+lpSubKey], 0
0x1800816d5  call    ConvertToNonHidden
0x1800816da  mov     edi, eax
0x1800816dc  test    eax, eax
0x1800816de  jz      short loc_180081758
0x1800816e0  cmp     eax, 0EBh
0x1800816e5  jz      short loc_180081758
0x1800816e7  mov     ebx, dword ptr [rbp+lpSubKey]
0x1800816ea  jmp     loc_1800817C8
0x1800816ef  mov     rcx, [rbp+hKey]
0x1800816f3  lea     r8, [rbp+lpSubKey]
0x1800816f7  xor     r9d, r9d
0x1800816fa  lea     rdx, aRegread; "RegRead"
0x180081701  call    RegReadFlag
0x180081706  test    eax, eax
0x180081708  jz      short loc_180081741
0x18008170a  mov     rcx, cs:WPP_GLOBAL_Control
0x180081711  lea     rdx, WPP_GLOBAL_Control
0x180081718  cmp     rcx, rdx
0x18008171b  jz      short loc_180081741
0x18008171d  test    byte ptr [rcx+1Ch], 80h
0x180081721  jz      short loc_180081741
0x180081723  cmp     byte ptr [rcx+19h], 2
0x180081727  jb      short loc_180081741
0x180081729  mov     rcx, [rcx+10h]
0x18008172d  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x180081734  mov     edx, 20h ; ' '
0x180081739  mov     r9d, eax
0x18008173c  call    WPP_SF_d
0x180081741  mov     rcx, [rbp+hKey]; hKey
0x180081745  call    cs:__imp_RegCloseKey
0x18008174b  mov     eax, dword ptr [rbp+lpSubKey]
0x18008174e  test    eax, eax
0x180081750  jnz     loc_1800816B2
0x180081756  jmp     short loc_1800817CF
0x180081758  mov     rcx, [rbp+hKey]; lpWideCharStr
0x18008175c  lea     r9, [rbp+lpSubKey]
0x180081760  lea     r8, [rbp+arg_18]
0x180081764  mov     rdx, rbx
0x180081767  call    RegistryPathConverter
0x18008176c  mov     ebx, eax
0x18008176e  test    eax, eax
0x180081770  jnz     short loc_1800817B3
0x180081772  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180081776  lea     rax, [rbp+var_10]
0x18008177a  mov     rcx, [rbp+arg_18]; hKey
0x18008177e  mov     r9d, 20219h; samDesired
0x180081784  xor     r8d, r8d; ulOptions
0x180081787  mov     [rsp+40h+phkResult], rax; phkResult
0x18008178c  call    cs:__imp_RegOpenKeyExA
0x180081792  cmp     [rbp+lpSubKey], 0
0x180081797  mov     ebx, eax
0x180081799  jz      short loc_1800817A5
0x18008179b  mov     rcx, [rbp+lpSubKey]; hMem
0x18008179f  call    cs:__imp_GlobalFree
0x1800817a5  test    ebx, ebx
0x1800817a7  jnz     short loc_1800817B3
0x1800817a9  mov     rcx, [rbp+var_10]; hKey
0x1800817ad  call    cs:__imp_RegCloseKey
0x1800817b3  test    edi, edi
0x1800817b5  jnz     short loc_1800817C8
0x1800817b7  cmp     [rbp+hKey], 0
0x1800817bc  jz      short loc_1800817C8
0x1800817be  mov     rcx, [rbp+hKey]; hMem
0x1800817c2  call    cs:__imp_GlobalFree
0x1800817c8  xor     eax, eax
0x1800817ca  test    ebx, ebx
0x1800817cc  setz    al
0x1800817cf  add     rsp, 40h
0x1800817d3  pop     rdi
0x1800817d4  pop     rbx
0x1800817d5  pop     rbp
0x1800817d6  retn
```
