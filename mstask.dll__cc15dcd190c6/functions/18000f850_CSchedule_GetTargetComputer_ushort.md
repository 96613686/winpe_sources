# CSchedule::GetTargetComputer(ushort * *)

- ea: `0x18000f850`
- end: `0x18000f964`
- name: `?GetTargetComputer@CSchedule@@UEAAJPEAPEAG@Z`
- size: `276`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001840`
- `0x18000f850`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8e9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18000f8df`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18000f8df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f912`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f912`

## pseudocode

```c
signed int __fastcall CSchedule::GetTargetComputer(CSchedule *this, unsigned __int16 **a2)
{
  signed int result; // eax
  const unsigned __int16 *v5; // rbx
  __int64 v6; // rax
  DWORD v7; // eax
  unsigned __int16 *v8; // rax
  int v9; // eax
  int v10; // ecx
  DWORD nSize[4]; // [rsp+20h] [rbp-238h] BYREF
  int v12; // [rsp+30h] [rbp-228h] BYREF
  WCHAR Buffer; // [rsp+34h] [rbp-224h] BYREF
  _BYTE v14[522]; // [rsp+36h] [rbp-222h] BYREF

  if ( !a2 )
    return -2147024809;
  v12 = *(_DWORD *)L"\\\\";
  Buffer = asc_18001E550[2];
  nSize[0] = 257;
  memset_0(v14, 0, 0x200u);
  v5 = (const unsigned __int16 *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    v7 = v6 + 1;
LABEL_11:
    nSize[0] = v7;
    v8 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v7);
    *a2 = v8;
    if ( !v8 )
      return -2147024882;
    v9 = StringCchCopyW(v8, nSize[0], v5);
    v10 = 0;
    if ( v9 < 0 )
      return v9;
    return v10;
  }
  if ( GetComputerNameW(&Buffer, nSize) )
  {
    v5 = (const unsigned __int16 *)&v12;
    v7 = nSize[0] + 3;
    goto LABEL_11;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000f850  mov     [rsp+arg_10], rbx
0x18000f855  mov     [rsp+arg_18], rsi
0x18000f85a  push    rdi
0x18000f85b  sub     rsp, 250h
0x18000f862  mov     rax, cs:__security_cookie
0x18000f869  xor     rax, rsp
0x18000f86c  mov     [rsp+258h+var_18], rax
0x18000f874  xor     esi, esi
0x18000f876  mov     rdi, rdx
0x18000f879  mov     rbx, rcx
0x18000f87c  test    rdx, rdx
0x18000f87f  jnz     short loc_18000F88B
0x18000f881  mov     eax, 80070057h
0x18000f886  jmp     loc_18000F93F
0x18000f88b  mov     eax, dword ptr cs:asc_18001E550; "\\\\"
0x18000f891  lea     rcx, [rsp+258h+var_222]; void *
0x18000f896  mov     [rsp+258h+var_228], eax
0x18000f89a  xor     edx, edx; Val
0x18000f89c  movzx   eax, word ptr cs:asc_18001E550+4; ""
0x18000f8a3  mov     r8d, 200h; Size
0x18000f8a9  mov     [rsp+258h+Buffer], ax
0x18000f8ae  mov     [rsp+258h+nSize], 101h
0x18000f8b6  call    memset_0
0x18000f8bb  mov     rbx, [rbx+38h]
0x18000f8bf  test    rbx, rbx
0x18000f8c2  jz      short loc_18000F8D5
0x18000f8c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f8c8  inc     rax
0x18000f8cb  cmp     [rbx+rax*2], si
0x18000f8cf  jnz     short loc_18000F8C8
0x18000f8d1  inc     eax
0x18000f8d3  jmp     short loc_18000F909
0x18000f8d5  lea     rdx, [rsp+258h+nSize]; nSize
0x18000f8da  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18000f8df  call    cs:__imp_GetComputerNameW
0x18000f8e5  test    eax, eax
0x18000f8e7  jnz     short loc_18000F8FD
0x18000f8e9  call    cs:__imp_GetLastError
0x18000f8ef  test    eax, eax
0x18000f8f1  jle     short loc_18000F93F
0x18000f8f3  movzx   eax, ax
0x18000f8f6  or      eax, 80070000h
0x18000f8fb  jmp     short loc_18000F93F
0x18000f8fd  mov     eax, [rsp+258h+nSize]
0x18000f901  lea     rbx, [rsp+258h+var_228]
0x18000f906  add     eax, 3
0x18000f909  mov     ecx, eax
0x18000f90b  add     rcx, rcx; cb
0x18000f90e  mov     [rsp+258h+nSize], eax
0x18000f912  call    cs:__imp_CoTaskMemAlloc
0x18000f918  mov     [rdi], rax
0x18000f91b  test    rax, rax
0x18000f91e  jnz     short loc_18000F927
0x18000f920  mov     eax, 8007000Eh
0x18000f925  jmp     short loc_18000F93F
0x18000f927  mov     edx, [rsp+258h+nSize]; unsigned __int64
0x18000f92b  mov     r8, rbx; unsigned __int16 *
0x18000f92e  mov     rcx, rax; unsigned __int16 *
0x18000f931  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f936  test    eax, eax
0x18000f938  mov     ecx, esi
0x18000f93a  cmovs   ecx, eax
0x18000f93d  mov     eax, ecx
0x18000f93f  mov     rcx, [rsp+258h+var_18]
0x18000f947  xor     rcx, rsp; StackCookie
0x18000f94a  call    __security_check_cookie
0x18000f94f  lea     r11, [rsp+258h+var_8]
0x18000f957  mov     rbx, [r11+20h]
0x18000f95b  mov     rsi, [r11+28h]
0x18000f95f  mov     rsp, r11
0x18000f962  pop     rdi
0x18000f963  retn
```
