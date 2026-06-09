# PerfDiagStartupResourceUtilizationReporting::FindSuccessorFileName(ushort *)

- ea: `0x1800c87d4`
- end: `0x1800c8954`
- name: `?FindSuccessorFileName@PerfDiagStartupResourceUtilizationReporting@@YAJPEAG@Z`
- size: `384`
- prototype: `signed int __fastcall(LPCWSTR lpFileName, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18002f06c`
- `0x1800c49c4`

## callees

- `0x180082b74`
- `0x1800c87d4`
- `0x1800cf04a`
- `0x1800cf080`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800c883d`
- `msvcrt!wcsrchr` at `0x1800c883d`
- `msvcrt!_itow_s` at `0x1800c88a3`
- `msvcrt!_itow_s` at `0x1800c8923`
- `msvcrt!_itow_s` at `0x1800c88a3`
- `msvcrt!_itow_s` at `0x1800c8923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c88c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c88c7`
- `KERNEL32!GetFileAttributesExW` at `0x1800c88bd`
- `KERNEL32!GetFileAttributesExW` at `0x1800c88bd`

## string_xrefs

- `0x1800c8868`: `.json`

## pseudocode

```c
signed int __fastcall PerfDiagStartupResourceUtilizationReporting::FindSuccessorFileName(
        LPCWSTR lpFileName,
        unsigned __int16 *a2)
{
  __int64 v2; // rdi
  int v4; // esi
  wchar_t *v5; // rax
  const wchar_t *v6; // rbx
  signed int result; // eax
  int v8; // r15d
  __int64 v9; // rdi
  unsigned __int64 v10; // rbx
  unsigned int v11; // r13d
  unsigned int i; // ebp
  wchar_t Buffer; // [rsp+20h] [rbp-88h] BYREF
  unsigned __int64 v14; // [rsp+28h] [rbp-80h]
  __int128 FileInformation; // [rsp+30h] [rbp-78h] BYREF
  __int128 v16; // [rsp+40h] [rbp-68h]
  int v17; // [rsp+50h] [rbp-58h]

  v14 = 0;
  FileInformation = 0;
  v17 = 0;
  v2 = -1;
  v16 = 0;
  do
    ++v2;
  while ( lpFileName[v2] );
  v4 = 5;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl) )
  {
    v5 = wcsrchr(lpFileName, 0x2Eu);
    v6 = v5;
    if ( !v5 )
      return -2147024809;
    if ( wcscmp_0(v5, L".xml") )
    {
      if ( wcscmp_0(v6, L".json") )
        return -2147024809;
      v4 = 6;
    }
  }
  v8 = 1;
  v9 = (unsigned int)(v2 - v4);
  v10 = 0;
  v11 = 0;
  for ( i = 1; i <= 5; ++i )
  {
    _itow_s(i, &Buffer, 2u, 10);
    lpFileName[v9] = Buffer;
    if ( GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
    {
      v14 = *(_QWORD *)((char *)&v16 + 4);
      if ( *(_QWORD *)((char *)&v16 + 4) > v10 )
      {
        v10 = v14;
        v11 = i;
      }
    }
    else
    {
      result = GetLastError();
      if ( result != 2 )
      {
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
        return result;
      }
    }
  }
  if ( v11 < 5 )
    v8 = v11 + 1;
  _itow_s(v8, &Buffer, 2u, 10);
  lpFileName[(unsigned int)v9] = Buffer;
  return 0;
}

```

## disassembly

```asm
0x1800c87d4  push    rbx
0x1800c87d6  push    rbp
0x1800c87d7  push    rsi
0x1800c87d8  push    rdi
0x1800c87d9  push    r12
0x1800c87db  push    r13
0x1800c87dd  push    r14
0x1800c87df  push    r15
0x1800c87e1  sub     rsp, 68h
0x1800c87e5  mov     rax, cs:__security_cookie
0x1800c87ec  xor     rax, rsp
0x1800c87ef  mov     [rsp+0A8h+var_50], rax
0x1800c87f4  xor     r12d, r12d
0x1800c87f7  xorps   xmm0, xmm0
0x1800c87fa  xor     eax, eax
0x1800c87fc  mov     [rsp+0A8h+var_80], r12
0x1800c8801  movups  [rsp+0A8h+FileInformation], xmm0
0x1800c8806  mov     [rsp+0A8h+var_58], eax
0x1800c880a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800c880e  movups  [rsp+0A8h+var_68], xmm0
0x1800c8813  mov     r14, rcx
0x1800c8816  inc     rdi
0x1800c8819  cmp     [rcx+rdi*2], r12w
0x1800c881e  jnz     short loc_1800C8816
0x1800c8820  mov     ebp, 5
0x1800c8825  mov     esi, ebp
0x1800c8827  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace> `wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl(void)'::`2'::impl
0x1800c882e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(void)
0x1800c8833  test    al, al
0x1800c8835  jz      short loc_1800C887E
0x1800c8837  lea     edx, [rbp+29h]; Ch
0x1800c883a  mov     rcx, r14; Str
0x1800c883d  call    cs:__imp_wcsrchr
0x1800c8843  mov     rbx, rax
0x1800c8846  test    rax, rax
0x1800c8849  jnz     short loc_1800C8855
0x1800c884b  mov     eax, 80070057h
0x1800c8850  jmp     loc_1800C8936
0x1800c8855  lea     rdx, aXml; ".xml"
0x1800c885c  mov     rcx, rbx; String1
0x1800c885f  call    wcscmp_0
0x1800c8864  test    eax, eax
0x1800c8866  jz      short loc_1800C887E
0x1800c8868  lea     rdx, aJson; ".json"
0x1800c886f  mov     rcx, rbx; String1
0x1800c8872  call    wcscmp_0
0x1800c8877  test    eax, eax
0x1800c8879  jnz     short loc_1800C884B
0x1800c887b  lea     esi, [rax+6]
0x1800c887e  mov     r15d, 1
0x1800c8884  sub     edi, esi
0x1800c8886  mov     rbx, r12
0x1800c8889  mov     r13d, r12d
0x1800c888c  mov     ebp, r15d
0x1800c888f  lea     esi, [r15+1]
0x1800c8893  mov     r9d, 0Ah; Radix
0x1800c8899  lea     rdx, [rsp+0A8h+Buffer]; Buffer
0x1800c889e  mov     r8, rsi; BufferCount
0x1800c88a1  mov     ecx, ebp; Value
0x1800c88a3  call    cs:__imp__itow_s
0x1800c88a9  movzx   eax, [rsp+0A8h+Buffer]
0x1800c88ae  lea     r8, [rsp+0A8h+FileInformation]; lpFileInformation
0x1800c88b3  xor     edx, edx; fInfoLevelId
0x1800c88b5  mov     [r14+rdi*2], ax
0x1800c88ba  mov     rcx, r14; lpFileName
0x1800c88bd  call    cs:__imp_GetFileAttributesExW
0x1800c88c3  test    eax, eax
0x1800c88c5  jnz     short loc_1800C88DF
0x1800c88c7  call    cs:__imp_GetLastError
0x1800c88cd  cmp     eax, esi
0x1800c88cf  jz      short loc_1800C88FE
0x1800c88d1  test    eax, eax
0x1800c88d3  jle     short loc_1800C8936
0x1800c88d5  movzx   eax, ax
0x1800c88d8  or      eax, 80070000h
0x1800c88dd  jmp     short loc_1800C8936
0x1800c88df  mov     eax, dword ptr [rsp+0A8h+var_68+4]
0x1800c88e3  mov     dword ptr [rsp+0A8h+var_80], eax
0x1800c88e7  mov     eax, dword ptr [rsp+0A8h+var_68+8]
0x1800c88eb  mov     dword ptr [rsp+0A8h+var_80+4], eax
0x1800c88ef  cmp     [rsp+0A8h+var_80], rbx
0x1800c88f4  jbe     short loc_1800C88FE
0x1800c88f6  mov     rbx, [rsp+0A8h+var_80]
0x1800c88fb  mov     r13d, ebp
0x1800c88fe  add     ebp, r15d
0x1800c8901  cmp     ebp, 5
0x1800c8904  jbe     short loc_1800C8893
0x1800c8906  cmp     r13d, 5
0x1800c890a  lea     eax, [r13+1]
0x1800c890e  mov     r9d, 0Ah; Radix
0x1800c8914  lea     rdx, [rsp+0A8h+Buffer]; Buffer
0x1800c8919  cmovb   r15d, eax
0x1800c891d  mov     r8, rsi; BufferCount
0x1800c8920  mov     ecx, r15d; Value
0x1800c8923  call    cs:__imp__itow_s
0x1800c8929  movzx   eax, [rsp+0A8h+Buffer]
0x1800c892e  mov     [r14+rdi*2], ax
0x1800c8933  mov     eax, r12d
0x1800c8936  mov     rcx, [rsp+0A8h+var_50]
0x1800c893b  xor     rcx, rsp; StackCookie
0x1800c893e  call    __security_check_cookie
0x1800c8943  add     rsp, 68h
0x1800c8947  pop     r15
0x1800c8949  pop     r14
0x1800c894b  pop     r13
0x1800c894d  pop     r12
0x1800c894f  pop     rdi
0x1800c8950  pop     rsi
0x1800c8951  pop     rbp
0x1800c8952  pop     rbx
0x1800c8953  retn
```
