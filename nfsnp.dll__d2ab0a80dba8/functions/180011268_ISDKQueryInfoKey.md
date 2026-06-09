# ISDKQueryInfoKey

- ea: `0x180011268`
- end: `0x18001141e`
- name: `ISDKQueryInfoKey`
- size: `438`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010e14`
- `0x180011038`

## callees

- `0x180001901`
- `0x180011268`
- `0x180011b62`

## import_xrefs

- `msvcrt!realloc` at `0x180011323`
- `msvcrt!realloc` at `0x180011323`
- `msvcrt!calloc` at `0x180011284`
- `msvcrt!calloc` at `0x1800112a0`
- `msvcrt!calloc` at `0x180011284`
- `msvcrt!calloc` at `0x1800112a0`
- `KERNEL32!SetLastError` at `0x1800113a5`
- `KERNEL32!SetLastError` at `0x1800113ed`
- `KERNEL32!SetLastError` at `0x180011404`
- `KERNEL32!SetLastError` at `0x1800113a5`
- `KERNEL32!SetLastError` at `0x1800113ed`
- `KERNEL32!SetLastError` at `0x180011404`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001138b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001138b`

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
0x180011268  push    rbx
0x18001126a  push    rbp
0x18001126b  push    rsi
0x18001126c  push    rdi
0x18001126d  push    r12
0x18001126f  push    r13
0x180011271  push    r14
0x180011273  push    r15
0x180011275  sub     rsp, 68h
0x180011279  mov     edx, 30h ; '0'; Size
0x18001127e  mov     r14, rcx
0x180011281  lea     ecx, [rdx-2Fh]; Count
0x180011284  call    cs:__imp_calloc
0x18001128a  mov     rbx, rax
0x18001128d  test    rax, rax
0x180011290  jz      loc_1800113FF
0x180011296  mov     edx, 2; Size
0x18001129b  mov     ecx, 104h; Count
0x1800112a0  call    cs:__imp_calloc
0x1800112a6  mov     [rbx], rax
0x1800112a9  test    rax, rax
0x1800112ac  jz      loc_1800113E8
0x1800112b2  lea     rdx, [rbx+18h]
0x1800112b6  mov     ebp, 104h
0x1800112bb  lea     r15, [rbx+28h]
0x1800112bf  mov     [rsp+0A8h+cchClass], ebp
0x1800112c6  mov     [rsp+0A8h+lpftLastWriteTime], r15
0x1800112cb  lea     r12, [rbx+24h]
0x1800112cf  mov     [rsp+0A8h+lpcbSecurityDescriptor], r12
0x1800112d4  lea     r13, [rbx+20h]
0x1800112d8  mov     [rsp+0A8h+lpcbMaxValueLen], r13
0x1800112dd  lea     rcx, [rbx+1Ch]
0x1800112e1  mov     [rsp+0A8h+lpcbMaxValueNameLen], rcx
0x1800112e6  lea     r8, [rbx+14h]
0x1800112ea  mov     [rsp+0A8h+lpcValues], rdx
0x1800112ef  lea     r9, [rbx+10h]
0x1800112f3  mov     [rsp+0A8h+lpcbMaxClassLen], r8
0x1800112f8  lea     r10, [rbx+8]
0x1800112fc  mov     [rsp+0A8h+lpcbMaxSubKeyLen], r9
0x180011301  mov     rdx, rax
0x180011304  mov     [rsp+0A8h+lpcSubKeys], r10
0x180011309  jmp     short loc_18001137D
0x18001130b  mov     rcx, [rbx]; Block
0x18001130e  add     ebp, 104h
0x180011314  mov     esi, ebp
0x180011316  add     rsi, rsi
0x180011319  mov     [rsp+0A8h+cchClass], ebp
0x180011320  mov     rdx, rsi; Size
0x180011323  call    cs:__imp_realloc
0x180011329  test    rax, rax
0x18001132c  jz      short loc_1800113A0
0x18001132e  mov     r8, rsi; Size
0x180011331  mov     [rbx], rax
0x180011334  xor     edx, edx; Val
0x180011336  mov     rcx, rax; void *
0x180011339  call    memset_0
0x18001133e  mov     rdx, [rbx]; lpClass
0x180011341  lea     rax, [rbx+1Ch]
0x180011345  mov     [rsp+0A8h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001134a  mov     [rsp+0A8h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18001134f  mov     [rsp+0A8h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180011354  mov     [rsp+0A8h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180011359  lea     rax, [rbx+18h]
0x18001135d  mov     [rsp+0A8h+lpcValues], rax; lpcValues
0x180011362  lea     rax, [rbx+14h]
0x180011366  mov     [rsp+0A8h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x18001136b  lea     rax, [rbx+10h]
0x18001136f  mov     [rsp+0A8h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180011374  lea     rax, [rbx+8]
0x180011378  mov     [rsp+0A8h+lpcSubKeys], rax; lpcSubKeys
0x18001137d  xor     r9d, r9d; lpReserved
0x180011380  lea     r8, [rsp+0A8h+cchClass]; lpcchClass
0x180011388  mov     rcx, r14; hKey
0x18001138b  call    cs:__imp_RegQueryInfoKeyW
0x180011391  mov     edi, eax
0x180011393  cmp     eax, 0EAh
0x180011398  jz      loc_18001130B
0x18001139e  jmp     short loc_1800113C9
0x1800113a0  mov     ecx, 8; dwErrCode
0x1800113a5  call    cs:__imp_SetLastError
0x1800113ab  mov     rcx, [rbx]; Block
0x1800113ae  test    rcx, rcx
0x1800113b1  jz      short loc_1800113BF
0x1800113b3  call    free_0
0x1800113b8  mov     qword ptr [rbx], 0
0x1800113bf  mov     rcx, rbx; Block
0x1800113c2  call    free_0
0x1800113c7  xor     ebx, ebx
0x1800113c9  test    edi, edi
0x1800113cb  jz      short loc_18001140A
0x1800113cd  test    rbx, rbx
0x1800113d0  jz      short loc_18001140A
0x1800113d2  mov     rcx, [rbx]; Block
0x1800113d5  test    rcx, rcx
0x1800113d8  jz      short loc_1800113F3
0x1800113da  call    free_0
0x1800113df  mov     qword ptr [rbx], 0
0x1800113e6  jmp     short loc_1800113F3
0x1800113e8  mov     ecx, 8; dwErrCode
0x1800113ed  call    cs:__imp_SetLastError
0x1800113f3  mov     rcx, rbx; Block
0x1800113f6  call    free_0
0x1800113fb  xor     ebx, ebx
0x1800113fd  jmp     short loc_18001140A
0x1800113ff  mov     ecx, 8; dwErrCode
0x180011404  call    cs:__imp_SetLastError
0x18001140a  mov     rax, rbx
0x18001140d  add     rsp, 68h
0x180011411  pop     r15
0x180011413  pop     r14
0x180011415  pop     r13
0x180011417  pop     r12
0x180011419  pop     rdi
0x18001141a  pop     rsi
0x18001141b  pop     rbp
0x18001141c  pop     rbx
0x18001141d  retn
```
