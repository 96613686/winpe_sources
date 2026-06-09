# DllGetClassObject

- ea: `0x180012ba0`
- end: `0x180012cb3`
- name: `DllGetClassObject`
- size: `275`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180012ba0`
- `0x180015010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180012c3d`
- `KERNEL32!EnterCriticalSection` at `0x180012c3d`
- `KERNEL32!LeaveCriticalSection` at `0x180012c6e`
- `KERNEL32!LeaveCriticalSection` at `0x180012c6e`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v7; // rcx
  __int64 *v8; // r9
  __int64 v9; // rsi
  _DWORD *v10; // rdx
  _QWORD *v11; // rdi

  if ( !ATL::_AtlComModule )
    return -2147418113;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = 0;
  v7 = off_18001D150;
  v8 = (__int64 *)off_18001D158;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_18001D158 )
  {
    v9 = *(_QWORD *)v7;
    if ( *(_QWORD *)v7 )
    {
      if ( *(_QWORD *)(v9 + 16) )
      {
        v10 = *(_DWORD **)v9;
        if ( rclsid->Data1 == **(_DWORD **)v9
          && *(_DWORD *)&rclsid->Data2 == v10[1]
          && *(_DWORD *)rclsid->Data4 == v10[2]
          && *(_DWORD *)&rclsid->Data4[4] == v10[3] )
        {
          v11 = (_QWORD *)(v9 + 32);
          if ( !*(_QWORD *)(v9 + 32) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v11 )
              v6 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v9 + 16))(
                     *(_QWORD *)(v9 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v9 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          if ( *v11 )
            v6 = (**(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *, __int64 *))*v11)(*v11, riid, ppv, v8);
          break;
        }
      }
    }
    v7 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v7 + 8);
  }
  if ( !*ppv && !v6 )
    return -2147221231;
  return v6;
}

```

## disassembly

```asm
0x180012ba0  push    rbx
0x180012ba2  push    rbp
0x180012ba3  push    rsi
0x180012ba4  push    rdi
0x180012ba5  push    r14
0x180012ba7  sub     rsp, 20h
0x180012bab  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180012bb2  mov     r14, r8
0x180012bb5  mov     r8, rcx
0x180012bb8  mov     rbp, rdx
0x180012bbb  jnz     short loc_180012BC7
0x180012bbd  mov     ebx, 8000FFFFh
0x180012bc2  jmp     loc_180012CA5
0x180012bc7  test    r14, r14
0x180012bca  jnz     short loc_180012BD6
0x180012bcc  mov     ebx, 80004003h
0x180012bd1  jmp     loc_180012CA5
0x180012bd6  mov     qword ptr [r14], 0
0x180012bdd  xor     ebx, ebx
0x180012bdf  mov     rcx, cs:off_18001D150
0x180012be6  mov     r9, cs:off_18001D158
0x180012bed  jmp     short loc_180012C26
0x180012bef  mov     rsi, [rcx]
0x180012bf2  test    rsi, rsi
0x180012bf5  jz      short loc_180012C22
0x180012bf7  cmp     [rsi+10h], rbx
0x180012bfb  jz      short loc_180012C22
0x180012bfd  mov     rdx, [rsi]
0x180012c00  mov     eax, [rdx]
0x180012c02  cmp     [r8], eax
0x180012c05  jnz     short loc_180012C22
0x180012c07  mov     eax, [rdx+4]
0x180012c0a  cmp     [r8+4], eax
0x180012c0e  jnz     short loc_180012C22
0x180012c10  mov     eax, [rdx+8]
0x180012c13  cmp     [r8+8], eax
0x180012c17  jnz     short loc_180012C22
0x180012c19  mov     eax, [rdx+0Ch]
0x180012c1c  cmp     [r8+0Ch], eax
0x180012c20  jz      short loc_180012C2D
0x180012c22  add     rcx, 8
0x180012c26  cmp     rcx, r9
0x180012c29  jb      short loc_180012BEF
0x180012c2b  jmp     short loc_180012C95
0x180012c2d  lea     rdi, [rsi+20h]
0x180012c31  cmp     [rdi], rbx
0x180012c34  jnz     short loc_180012C7A
0x180012c36  lea     rcx, CriticalSection; lpCriticalSection
0x180012c3d  call    cs:__imp_EnterCriticalSection
0x180012c44  nop     dword ptr [rax+rax+00h]
0x180012c49  cmp     [rdi], rbx
0x180012c4c  jnz     short loc_180012C67
0x180012c4e  mov     rcx, [rsi+18h]
0x180012c52  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180012c59  mov     rax, [rsi+10h]
0x180012c5d  mov     r8, rdi
0x180012c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c65  mov     ebx, eax
0x180012c67  lea     rcx, CriticalSection; lpCriticalSection
0x180012c6e  call    cs:__imp_LeaveCriticalSection
0x180012c75  nop     dword ptr [rax+rax+00h]
0x180012c7a  mov     rcx, [rdi]
0x180012c7d  test    rcx, rcx
0x180012c80  jz      short loc_180012C95
0x180012c82  mov     rax, [rcx]
0x180012c85  mov     r8, r14
0x180012c88  mov     rdx, rbp
0x180012c8b  mov     rax, [rax]
0x180012c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c93  mov     ebx, eax
0x180012c95  cmp     qword ptr [r14], 0
0x180012c99  jnz     short loc_180012CA5
0x180012c9b  test    ebx, ebx
0x180012c9d  mov     eax, 80040111h
0x180012ca2  cmovz   ebx, eax
0x180012ca5  mov     eax, ebx
0x180012ca7  add     rsp, 20h
0x180012cab  pop     r14
0x180012cad  pop     rdi
0x180012cae  pop     rsi
0x180012caf  pop     rbp
0x180012cb0  pop     rbx
0x180012cb1  retn
```
