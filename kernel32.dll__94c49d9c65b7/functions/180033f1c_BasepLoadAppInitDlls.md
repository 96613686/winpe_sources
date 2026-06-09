# BasepLoadAppInitDlls

- ea: `0x180033f1c`
- end: `0x1800340d0`
- name: `BasepLoadAppInitDlls`
- size: `436`
- prototype: `__int64 __fastcall(HKEY hkey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180033ac0`

## callees

- `0x180033f1c`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180034070`
- `ntdll!RtlFreeHeap` at `0x1800340c5`
- `ntdll!RtlFreeHeap` at `0x180034070`
- `ntdll!RtlFreeHeap` at `0x1800340c5`
- `ntdll!RtlAllocateHeap` at `0x18003408a`
- `ntdll!RtlAllocateHeap` at `0x18003408a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033f73`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033fb4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033f73`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033fb4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034011`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034011`

## string_xrefs

- `0x180033f9e`: `AppInit_DLLs`
- `0x180033f52`: `RequireSignedAppInit_DLLs`

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
0x180033f1c  push    rbx
0x180033f1e  push    rbp
0x180033f1f  push    rsi
0x180033f20  push    rdi
0x180033f21  sub     rsp, 168h
0x180033f28  mov     rax, cs:__security_cookie
0x180033f2f  xor     rax, rsp
0x180033f32  mov     [rsp+188h+var_38], rax
0x180033f3a  xor     ebp, ebp
0x180033f3c  mov     [rsp+188h+var_148], 4
0x180033f44  lea     rax, [rsp+188h+var_148]
0x180033f49  mov     [rsp+188h+var_144], ebp
0x180033f4d  mov     [rsp+188h+pcbData], rax; pcbData
0x180033f52  lea     r8, aRequiresigneda; "RequireSignedAppInit_DLLs"
0x180033f59  lea     rax, [rsp+188h+var_144]
0x180033f5e  xor     edx, edx; lpSubKey
0x180033f60  mov     [rsp+188h+pvData], rax; pvData
0x180033f65  lea     r9d, [rbp+10h]; dwFlags
0x180033f69  mov     [rsp+188h+pdwType], rbp; pdwType
0x180033f6e  mov     rbx, rcx
0x180033f71  mov     esi, ebp
0x180033f73  call    cs:__imp_RegGetValueW
0x180033f79  test    eax, eax
0x180033f7b  jz      loc_180034043
0x180033f81  lea     rdi, [rsp+188h+LibFileName]
0x180033f86  mov     [rsp+188h+var_148], 100h
0x180033f8e  lea     rax, [rsp+188h+var_148]
0x180033f93  mov     r9d, 2; dwFlags
0x180033f99  mov     [rsp+188h+pcbData], rax; pcbData
0x180033f9e  lea     r8, aAppinitDlls; "AppInit_DLLs"
0x180033fa5  mov     [rsp+188h+pvData], rdi; pvData
0x180033faa  xor     edx, edx; lpSubKey
0x180033fac  mov     rcx, rbx; hkey
0x180033faf  mov     [rsp+188h+pdwType], rbp; pdwType
0x180033fb4  call    cs:__imp_RegGetValueW
0x180033fba  cmp     eax, 0EAh
0x180033fbf  jz      loc_180034054
0x180033fc5  test    eax, eax
0x180033fc7  jnz     short loc_180034019
0x180033fc9  mov     rbx, rdi
0x180033fcc  movzx   eax, word ptr [rbx]
0x180033fcf  cmp     ax, 20h ; ' '
0x180033fd3  jz      loc_18003409E
0x180033fd9  cmp     ax, 2Ch ; ','
0x180033fdd  jz      loc_18003409E
0x180033fe3  test    ax, ax
0x180033fe6  jz      short loc_180034019
0x180033fe8  mov     rcx, rbx; lpLibFileName
0x180033feb  cmp     ax, 2Ch ; ','
0x180033fef  jz      short loc_180034003
0x180033ff1  test    ax, ax
0x180033ff4  jz      short loc_180034003
0x180033ff6  add     rbx, 2
0x180033ffa  movzx   eax, word ptr [rbx]
0x180033ffd  cmp     ax, 20h ; ' '
0x180034001  jnz     short loc_180033FEB
0x180034003  cmp     [rbx], bp
0x180034006  jnz     loc_1800340A7
0x18003400c  mov     r8d, esi; dwFlags
0x18003400f  xor     edx, edx; hFile
0x180034011  call    cs:__imp_LoadLibraryExW
0x180034017  jmp     short loc_180033FCC
0x180034019  lea     rax, [rsp+188h+LibFileName]
0x18003401e  cmp     rdi, rax
0x180034021  jnz     loc_1800340B3
0x180034027  mov     rcx, [rsp+188h+var_38]
0x18003402f  xor     rcx, rsp; StackCookie
0x180034032  call    __security_check_cookie
0x180034037  add     rsp, 168h
0x18003403e  pop     rdi
0x18003403f  pop     rsi
0x180034040  pop     rbp
0x180034041  pop     rbx
0x180034042  retn
0x180034043  cmp     [rsp+188h+var_144], ebp
0x180034047  mov     eax, 80h
0x18003404c  cmovnz  esi, eax
0x18003404f  jmp     loc_180033F81
0x180034054  lea     rax, [rsp+188h+LibFileName]
0x180034059  cmp     rdi, rax
0x18003405c  jz      short loc_180034076
0x18003405e  mov     rcx, gs:60h
0x180034067  mov     r8, rdi; P
0x18003406a  xor     edx, edx; Flags
0x18003406c  mov     rcx, [rcx+30h]; HeapHandle
0x180034070  call    cs:__imp_RtlFreeHeap
0x180034076  mov     rcx, gs:60h
0x18003407f  xor     edx, edx; Flags
0x180034081  mov     r8d, [rsp+188h+var_148]; Size
0x180034086  mov     rcx, [rcx+30h]; HeapHandle
0x18003408a  call    cs:__imp_RtlAllocateHeap
0x180034090  mov     rdi, rax
0x180034093  test    rax, rax
0x180034096  jnz     loc_180033F8E
0x18003409c  jmp     short loc_180034027
0x18003409e  add     rbx, 2
0x1800340a2  jmp     loc_180033FCC
0x1800340a7  mov     [rbx], bp
0x1800340aa  add     rbx, 2
0x1800340ae  jmp     loc_18003400C
0x1800340b3  mov     rcx, gs:60h
0x1800340bc  mov     r8, rdi; P
0x1800340bf  xor     edx, edx; Flags
0x1800340c1  mov     rcx, [rcx+30h]; HeapHandle
0x1800340c5  call    cs:__imp_RtlFreeHeap
0x1800340cb  jmp     loc_180034027
```
