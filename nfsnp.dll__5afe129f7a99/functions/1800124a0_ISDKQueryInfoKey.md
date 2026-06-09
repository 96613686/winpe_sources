# ISDKQueryInfoKey

- ea: `0x1800124a0`
- end: `0x180012681`
- name: `ISDKQueryInfoKey`
- size: `481`
- prototype: `struct _FILETIME *__fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180011fec`
- `0x180012240`

## callees

- `0x180001901`
- `0x1800124a0`
- `0x180012e32`

## import_xrefs

- `msvcrt!realloc` at `0x180012567`
- `msvcrt!realloc` at `0x180012567`
- `msvcrt!calloc` at `0x1800124bc`
- `msvcrt!calloc` at `0x1800124de`
- `msvcrt!calloc` at `0x1800124bc`
- `msvcrt!calloc` at `0x1800124de`
- `KERNEL32!SetLastError` at `0x1800125f5`
- `KERNEL32!SetLastError` at `0x180012643`
- `KERNEL32!SetLastError` at `0x180012660`
- `KERNEL32!SetLastError` at `0x1800125f5`
- `KERNEL32!SetLastError` at `0x180012643`
- `KERNEL32!SetLastError` at `0x180012660`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800125d5`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800125d5`

## pseudocode

```c
struct _FILETIME *__fastcall ISDKQueryInfoKey(HKEY hKey)
{
  struct _FILETIME *v2; // rbx
  WCHAR *v3; // rax
  DWORD v4; // ebp
  LSTATUS i; // eax
  void *v6; // rcx
  void *v7; // rax
  LSTATUS v8; // edi
  DWORD cchClass; // [rsp+B8h] [rbp+10h] BYREF

  v2 = (struct _FILETIME *)calloc(1u, 0x30u);
  if ( !v2 )
  {
    SetLastError(8u);
    return v2;
  }
  v3 = (WCHAR *)calloc(0x104u, 2u);
  *v2 = (struct _FILETIME)v3;
  if ( !v3 )
  {
    SetLastError(8u);
LABEL_16:
    free_0(v2);
    return 0;
  }
  v4 = 260;
  cchClass = 260;
  for ( i = RegQueryInfoKeyW(
              hKey,
              v3,
              &cchClass,
              0,
              (LPDWORD)&v2[1],
              (LPDWORD)&v2[2],
              &v2[2].dwHighDateTime,
              (LPDWORD)&v2[3],
              &v2[3].dwHighDateTime,
              (LPDWORD)&v2[4],
              &v2[4].dwHighDateTime,
              v2 + 5);
        ;
        i = RegQueryInfoKeyW(
              hKey,
              *(LPWSTR *)v2,
              &cchClass,
              0,
              (LPDWORD)&v2[1],
              (LPDWORD)&v2[2],
              &v2[2].dwHighDateTime,
              (LPDWORD)&v2[3],
              &v2[3].dwHighDateTime,
              (LPDWORD)&v2[4],
              &v2[4].dwHighDateTime,
              v2 + 5) )
  {
    v8 = i;
    if ( i != 234 )
      break;
    v6 = (void *)*v2;
    v4 += 260;
    cchClass = v4;
    v7 = realloc(v6, 2LL * v4);
    if ( !v7 )
    {
      SetLastError(8u);
      if ( *v2 )
      {
        free_0(*(void **)v2);
        *v2 = 0;
      }
      free_0(v2);
      v2 = 0;
      break;
    }
    *v2 = (struct _FILETIME)v7;
    memset_0(v7, 0, 2LL * v4);
  }
  if ( v8 && v2 )
  {
    if ( *v2 )
    {
      free_0(*(void **)v2);
      *v2 = 0;
    }
    goto LABEL_16;
  }
  return v2;
}

```

## disassembly

```asm
0x1800124a0  push    rbx
0x1800124a2  push    rbp
0x1800124a3  push    rsi
0x1800124a4  push    rdi
0x1800124a5  push    r12
0x1800124a7  push    r13
0x1800124a9  push    r14
0x1800124ab  push    r15
0x1800124ad  sub     rsp, 68h
0x1800124b1  mov     edx, 30h ; '0'; Size
0x1800124b6  mov     r14, rcx
0x1800124b9  lea     ecx, [rdx-2Fh]; Count
0x1800124bc  call    cs:__imp_calloc
0x1800124c3  nop     dword ptr [rax+rax+00h]
0x1800124c8  mov     rbx, rax
0x1800124cb  test    rax, rax
0x1800124ce  jz      loc_18001265B
0x1800124d4  mov     edx, 2; Size
0x1800124d9  mov     ecx, 104h; Count
0x1800124de  call    cs:__imp_calloc
0x1800124e5  nop     dword ptr [rax+rax+00h]
0x1800124ea  mov     [rbx], rax
0x1800124ed  test    rax, rax
0x1800124f0  jz      loc_18001263E
0x1800124f6  lea     rdx, [rbx+18h]
0x1800124fa  mov     ebp, 104h
0x1800124ff  lea     r15, [rbx+28h]
0x180012503  mov     [rsp+0A8h+cchClass], ebp
0x18001250a  mov     [rsp+0A8h+lpftLastWriteTime], r15
0x18001250f  lea     r12, [rbx+24h]
0x180012513  mov     [rsp+0A8h+lpcbSecurityDescriptor], r12
0x180012518  lea     r13, [rbx+20h]
0x18001251c  mov     [rsp+0A8h+lpcbMaxValueLen], r13
0x180012521  lea     rcx, [rbx+1Ch]
0x180012525  mov     [rsp+0A8h+lpcbMaxValueNameLen], rcx
0x18001252a  lea     r8, [rbx+14h]
0x18001252e  mov     [rsp+0A8h+lpcValues], rdx
0x180012533  lea     r9, [rbx+10h]
0x180012537  mov     [rsp+0A8h+lpcbMaxClassLen], r8
0x18001253c  lea     r10, [rbx+8]
0x180012540  mov     [rsp+0A8h+lpcbMaxSubKeyLen], r9
0x180012545  mov     rdx, rax
0x180012548  mov     [rsp+0A8h+lpcSubKeys], r10
0x18001254d  jmp     short loc_1800125C7
0x18001254f  mov     rcx, [rbx]; Block
0x180012552  add     ebp, 104h
0x180012558  mov     esi, ebp
0x18001255a  add     rsi, rsi
0x18001255d  mov     [rsp+0A8h+cchClass], ebp
0x180012564  mov     rdx, rsi; Size
0x180012567  call    cs:__imp_realloc
0x18001256e  nop     dword ptr [rax+rax+00h]
0x180012573  test    rax, rax
0x180012576  jz      short loc_1800125F0
0x180012578  mov     r8, rsi; Size
0x18001257b  mov     [rbx], rax
0x18001257e  xor     edx, edx; Val
0x180012580  mov     rcx, rax; void *
0x180012583  call    memset_0
0x180012588  mov     rdx, [rbx]; lpClass
0x18001258b  lea     rax, [rbx+1Ch]
0x18001258f  mov     [rsp+0A8h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180012594  mov     [rsp+0A8h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180012599  mov     [rsp+0A8h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18001259e  mov     [rsp+0A8h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800125a3  lea     rax, [rbx+18h]
0x1800125a7  mov     [rsp+0A8h+lpcValues], rax; lpcValues
0x1800125ac  lea     rax, [rbx+14h]
0x1800125b0  mov     [rsp+0A8h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x1800125b5  lea     rax, [rbx+10h]
0x1800125b9  mov     [rsp+0A8h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800125be  lea     rax, [rbx+8]
0x1800125c2  mov     [rsp+0A8h+lpcSubKeys], rax; lpcSubKeys
0x1800125c7  xor     r9d, r9d; lpReserved
0x1800125ca  lea     r8, [rsp+0A8h+cchClass]; lpcchClass
0x1800125d2  mov     rcx, r14; hKey
0x1800125d5  call    cs:__imp_RegQueryInfoKeyW
0x1800125dc  nop     dword ptr [rax+rax+00h]
0x1800125e1  mov     edi, eax
0x1800125e3  cmp     eax, 0EAh
0x1800125e8  jz      loc_18001254F
0x1800125ee  jmp     short loc_18001261F
0x1800125f0  mov     ecx, 8; dwErrCode
0x1800125f5  call    cs:__imp_SetLastError
0x1800125fc  nop     dword ptr [rax+rax+00h]
0x180012601  mov     rcx, [rbx]; Block
0x180012604  test    rcx, rcx
0x180012607  jz      short loc_180012615
0x180012609  call    free_0
0x18001260e  mov     qword ptr [rbx], 0
0x180012615  mov     rcx, rbx; Block
0x180012618  call    free_0
0x18001261d  xor     ebx, ebx
0x18001261f  test    edi, edi
0x180012621  jz      short loc_18001266C
0x180012623  test    rbx, rbx
0x180012626  jz      short loc_18001266C
0x180012628  mov     rcx, [rbx]; Block
0x18001262b  test    rcx, rcx
0x18001262e  jz      short loc_18001264F
0x180012630  call    free_0
0x180012635  mov     qword ptr [rbx], 0
0x18001263c  jmp     short loc_18001264F
0x18001263e  mov     ecx, 8; dwErrCode
0x180012643  call    cs:__imp_SetLastError
0x18001264a  nop     dword ptr [rax+rax+00h]
0x18001264f  mov     rcx, rbx; Block
0x180012652  call    free_0
0x180012657  xor     ebx, ebx
0x180012659  jmp     short loc_18001266C
0x18001265b  mov     ecx, 8; dwErrCode
0x180012660  call    cs:__imp_SetLastError
0x180012667  nop     dword ptr [rax+rax+00h]
0x18001266c  mov     rax, rbx
0x18001266f  add     rsp, 68h
0x180012673  pop     r15
0x180012675  pop     r14
0x180012677  pop     r13
0x180012679  pop     r12
0x18001267b  pop     rdi
0x18001267c  pop     rsi
0x18001267d  pop     rbp
0x18001267e  pop     rbx
0x18001267f  retn
```
