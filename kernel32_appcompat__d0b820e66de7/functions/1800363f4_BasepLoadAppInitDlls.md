# BasepLoadAppInitDlls

- ea: `0x1800363f4`
- end: `0x1800365d0`
- name: `BasepLoadAppInitDlls`
- size: `476`
- prototype: `__int64 __fastcall(HKEY hkey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180035f10`

## callees

- `0x1800363f4`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003655b`
- `ntdll!RtlFreeHeap` at `0x1800365bf`
- `ntdll!RtlFreeHeap` at `0x18003655b`
- `ntdll!RtlFreeHeap` at `0x1800365bf`
- `ntdll!RtlAllocateHeap` at `0x18003657b`
- `ntdll!RtlAllocateHeap` at `0x18003657b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003644b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036492`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003644b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036492`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800364f5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800364f5`

## string_xrefs

- `0x18003647c`: `AppInit_DLLs`
- `0x18003642a`: `RequireSignedAppInit_DLLs`

## pseudocode

```c
char __fastcall BasepLoadAppInitDlls(HKEY hkey)
{
  DWORD v2; // esi
  WCHAR *v3; // rdi
  LSTATUS ValueW; // eax
  WCHAR *v5; // rbx
  WCHAR v6; // ax
  const WCHAR *v7; // rcx
  WCHAR *Heap; // rax
  DWORD pcbData; // [rsp+40h] [rbp-148h] BYREF
  _DWORD pvData[3]; // [rsp+44h] [rbp-144h] BYREF
  WCHAR LibFileName[128]; // [rsp+50h] [rbp-138h] BYREF

  pcbData = 4;
  pvData[0] = 0;
  v2 = 0;
  if ( !RegGetValueW(hkey, 0, L"RequireSignedAppInit_DLLs", 0x10u, 0, pvData, &pcbData) && pvData[0] )
    v2 = 128;
  v3 = LibFileName;
  pcbData = 256;
  while ( 1 )
  {
    ValueW = RegGetValueW(hkey, 0, L"AppInit_DLLs", 2u, 0, v3, &pcbData);
    if ( ValueW != 234 )
      break;
    if ( v3 != LibFileName )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, pcbData);
    v3 = Heap;
    if ( !Heap )
      return (char)Heap;
  }
  if ( !ValueW )
  {
    v5 = v3;
    while ( 1 )
    {
      while ( 1 )
      {
        v6 = *v5;
        if ( *v5 != 32 && v6 != 44 )
          break;
        ++v5;
      }
      if ( !v6 )
        break;
      v7 = v5;
      do
      {
        if ( v6 == 44 )
          break;
        if ( !v6 )
          break;
        v6 = *++v5;
      }
      while ( *v5 != 32 );
      if ( *v5 )
        *v5++ = 0;
      LoadLibraryExW(v7, 0, v2);
    }
  }
  Heap = LibFileName;
  if ( v3 != LibFileName )
    LOBYTE(Heap) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  return (char)Heap;
}

```

## disassembly

```asm
0x1800363f4  push    rbx
0x1800363f6  push    rbp
0x1800363f7  push    rsi
0x1800363f8  push    rdi
0x1800363f9  sub     rsp, 168h
0x180036400  mov     rax, cs:__security_cookie
0x180036407  xor     rax, rsp
0x18003640a  mov     [rsp+188h+var_38], rax
0x180036412  xor     ebp, ebp
0x180036414  mov     [rsp+188h+var_148], 4
0x18003641c  lea     rax, [rsp+188h+var_148]
0x180036421  mov     [rsp+188h+var_144], ebp
0x180036425  mov     [rsp+188h+pcbData], rax; pcbData
0x18003642a  lea     r8, aRequiresigneda; "RequireSignedAppInit_DLLs"
0x180036431  lea     rax, [rsp+188h+var_144]
0x180036436  xor     edx, edx; lpSubKey
0x180036438  mov     [rsp+188h+pvData], rax; pvData
0x18003643d  lea     r9d, [rbp+10h]; dwFlags
0x180036441  mov     [rsp+188h+pdwType], rbp; pdwType
0x180036446  mov     rbx, rcx
0x180036449  mov     esi, ebp
0x18003644b  call    cs:__imp_RegGetValueW
0x180036452  nop     dword ptr [rax+rax+00h]
0x180036457  test    eax, eax
0x180036459  jz      loc_18003652E
0x18003645f  lea     rdi, [rsp+188h+LibFileName]
0x180036464  mov     [rsp+188h+var_148], 100h
0x18003646c  lea     rax, [rsp+188h+var_148]
0x180036471  mov     r9d, 2; dwFlags
0x180036477  mov     [rsp+188h+pcbData], rax; pcbData
0x18003647c  lea     r8, aAppinitDlls; "AppInit_DLLs"
0x180036483  mov     [rsp+188h+pvData], rdi; pvData
0x180036488  xor     edx, edx; lpSubKey
0x18003648a  mov     rcx, rbx; hkey
0x18003648d  mov     [rsp+188h+pdwType], rbp; pdwType
0x180036492  call    cs:__imp_RegGetValueW
0x180036499  nop     dword ptr [rax+rax+00h]
0x18003649e  cmp     eax, 0EAh
0x1800364a3  jz      loc_18003653F
0x1800364a9  test    eax, eax
0x1800364ab  jnz     short loc_180036503
0x1800364ad  mov     rbx, rdi
0x1800364b0  movzx   eax, word ptr [rbx]
0x1800364b3  cmp     ax, 20h ; ' '
0x1800364b7  jz      loc_180036598
0x1800364bd  cmp     ax, 2Ch ; ','
0x1800364c1  jz      loc_180036598
0x1800364c7  test    ax, ax
0x1800364ca  jz      short loc_180036503
0x1800364cc  mov     rcx, rbx; lpLibFileName
0x1800364cf  cmp     ax, 2Ch ; ','
0x1800364d3  jz      short loc_1800364E7
0x1800364d5  test    ax, ax
0x1800364d8  jz      short loc_1800364E7
0x1800364da  add     rbx, 2
0x1800364de  movzx   eax, word ptr [rbx]
0x1800364e1  cmp     ax, 20h ; ' '
0x1800364e5  jnz     short loc_1800364CF
0x1800364e7  cmp     [rbx], bp
0x1800364ea  jnz     loc_1800365A1
0x1800364f0  mov     r8d, esi; dwFlags
0x1800364f3  xor     edx, edx; hFile
0x1800364f5  call    cs:__imp_LoadLibraryExW
0x1800364fc  nop     dword ptr [rax+rax+00h]
0x180036501  jmp     short loc_1800364B0
0x180036503  lea     rax, [rsp+188h+LibFileName]
0x180036508  cmp     rdi, rax
0x18003650b  jnz     loc_1800365AD
0x180036511  mov     rcx, [rsp+188h+var_38]
0x180036519  xor     rcx, rsp; StackCookie
0x18003651c  call    __security_check_cookie
0x180036521  add     rsp, 168h
0x180036528  pop     rdi
0x180036529  pop     rsi
0x18003652a  pop     rbp
0x18003652b  pop     rbx
0x18003652c  retn
0x18003652e  cmp     [rsp+188h+var_144], ebp
0x180036532  mov     eax, 80h
0x180036537  cmovnz  esi, eax
0x18003653a  jmp     loc_18003645F
0x18003653f  lea     rax, [rsp+188h+LibFileName]
0x180036544  cmp     rdi, rax
0x180036547  jz      short loc_180036567
0x180036549  mov     rcx, gs:60h
0x180036552  mov     r8, rdi; P
0x180036555  xor     edx, edx; Flags
0x180036557  mov     rcx, [rcx+30h]; HeapHandle
0x18003655b  call    cs:__imp_RtlFreeHeap
0x180036562  nop     dword ptr [rax+rax+00h]
0x180036567  mov     rcx, gs:60h
0x180036570  xor     edx, edx; Flags
0x180036572  mov     r8d, [rsp+188h+var_148]; Size
0x180036577  mov     rcx, [rcx+30h]; HeapHandle
0x18003657b  call    cs:__imp_RtlAllocateHeap
0x180036582  nop     dword ptr [rax+rax+00h]
0x180036587  mov     rdi, rax
0x18003658a  test    rax, rax
0x18003658d  jnz     loc_18003646C
0x180036593  jmp     loc_180036511
0x180036598  add     rbx, 2
0x18003659c  jmp     loc_1800364B0
0x1800365a1  mov     [rbx], bp
0x1800365a4  add     rbx, 2
0x1800365a8  jmp     loc_1800364F0
0x1800365ad  mov     rcx, gs:60h
0x1800365b6  mov     r8, rdi; P
0x1800365b9  xor     edx, edx; Flags
0x1800365bb  mov     rcx, [rcx+30h]; HeapHandle
0x1800365bf  call    cs:__imp_RtlFreeHeap
0x1800365c6  nop     dword ptr [rax+rax+00h]
0x1800365cb  jmp     loc_180036511
```
