# DllGetClassObject

- ea: `0x180005cf0`
- end: `0x180005e03`
- name: `DllGetClassObject`
- size: `275`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005cf0`
- `0x18000f010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180005dbe`
- `KERNEL32!LeaveCriticalSection` at `0x180005dbe`
- `KERNEL32!EnterCriticalSection` at `0x180005d8d`
- `KERNEL32!EnterCriticalSection` at `0x180005d8d`

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
  v7 = off_180017350;
  v8 = (__int64 *)off_180017358;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_180017358 )
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
0x180005cf0  push    rbx
0x180005cf2  push    rbp
0x180005cf3  push    rsi
0x180005cf4  push    rdi
0x180005cf5  push    r14
0x180005cf7  sub     rsp, 20h
0x180005cfb  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180005d02  mov     r14, r8
0x180005d05  mov     r8, rcx
0x180005d08  mov     rbp, rdx
0x180005d0b  jnz     short loc_180005D17
0x180005d0d  mov     ebx, 8000FFFFh
0x180005d12  jmp     loc_180005DF5
0x180005d17  test    r14, r14
0x180005d1a  jnz     short loc_180005D26
0x180005d1c  mov     ebx, 80004003h
0x180005d21  jmp     loc_180005DF5
0x180005d26  mov     qword ptr [r14], 0
0x180005d2d  xor     ebx, ebx
0x180005d2f  mov     rcx, cs:off_180017350
0x180005d36  mov     r9, cs:off_180017358
0x180005d3d  jmp     short loc_180005D76
0x180005d3f  mov     rsi, [rcx]
0x180005d42  test    rsi, rsi
0x180005d45  jz      short loc_180005D72
0x180005d47  cmp     [rsi+10h], rbx
0x180005d4b  jz      short loc_180005D72
0x180005d4d  mov     rdx, [rsi]
0x180005d50  mov     eax, [rdx]
0x180005d52  cmp     [r8], eax
0x180005d55  jnz     short loc_180005D72
0x180005d57  mov     eax, [rdx+4]
0x180005d5a  cmp     [r8+4], eax
0x180005d5e  jnz     short loc_180005D72
0x180005d60  mov     eax, [rdx+8]
0x180005d63  cmp     [r8+8], eax
0x180005d67  jnz     short loc_180005D72
0x180005d69  mov     eax, [rdx+0Ch]
0x180005d6c  cmp     [r8+0Ch], eax
0x180005d70  jz      short loc_180005D7D
0x180005d72  add     rcx, 8
0x180005d76  cmp     rcx, r9
0x180005d79  jb      short loc_180005D3F
0x180005d7b  jmp     short loc_180005DE5
0x180005d7d  lea     rdi, [rsi+20h]
0x180005d81  cmp     [rdi], rbx
0x180005d84  jnz     short loc_180005DCA
0x180005d86  lea     rcx, CriticalSection; lpCriticalSection
0x180005d8d  call    cs:__imp_EnterCriticalSection
0x180005d94  nop     dword ptr [rax+rax+00h]
0x180005d99  cmp     [rdi], rbx
0x180005d9c  jnz     short loc_180005DB7
0x180005d9e  mov     rcx, [rsi+18h]
0x180005da2  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180005da9  mov     rax, [rsi+10h]
0x180005dad  mov     r8, rdi
0x180005db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db5  mov     ebx, eax
0x180005db7  lea     rcx, CriticalSection; lpCriticalSection
0x180005dbe  call    cs:__imp_LeaveCriticalSection
0x180005dc5  nop     dword ptr [rax+rax+00h]
0x180005dca  mov     rcx, [rdi]
0x180005dcd  test    rcx, rcx
0x180005dd0  jz      short loc_180005DE5
0x180005dd2  mov     rax, [rcx]
0x180005dd5  mov     r8, r14
0x180005dd8  mov     rdx, rbp
0x180005ddb  mov     rax, [rax]
0x180005dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de3  mov     ebx, eax
0x180005de5  cmp     qword ptr [r14], 0
0x180005de9  jnz     short loc_180005DF5
0x180005deb  test    ebx, ebx
0x180005ded  mov     eax, 80040111h
0x180005df2  cmovz   ebx, eax
0x180005df5  mov     eax, ebx
0x180005df7  add     rsp, 20h
0x180005dfb  pop     r14
0x180005dfd  pop     rdi
0x180005dfe  pop     rsi
0x180005dff  pop     rbp
0x180005e00  pop     rbx
0x180005e01  retn
```
