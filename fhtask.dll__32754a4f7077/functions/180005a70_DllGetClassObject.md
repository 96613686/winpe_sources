# DllGetClassObject

- ea: `0x180005a70`
- end: `0x180005b76`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005a70`
- `0x18000b010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180005b0d`
- `KERNEL32!EnterCriticalSection` at `0x180005b0d`
- `KERNEL32!LeaveCriticalSection` at `0x180005b38`
- `KERNEL32!LeaveCriticalSection` at `0x180005b38`

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
  v7 = off_180010160;
  v8 = (__int64 *)off_180010168;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_180010168 )
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
0x180005a70  push    rbx
0x180005a72  push    rbp
0x180005a73  push    rsi
0x180005a74  push    rdi
0x180005a75  push    r14
0x180005a77  sub     rsp, 20h
0x180005a7b  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180005a82  mov     r14, r8
0x180005a85  mov     r8, rcx
0x180005a88  mov     rbp, rdx
0x180005a8b  jnz     short loc_180005A97
0x180005a8d  mov     ebx, 8000FFFFh
0x180005a92  jmp     loc_180005B69
0x180005a97  test    r14, r14
0x180005a9a  jnz     short loc_180005AA6
0x180005a9c  mov     ebx, 80004003h
0x180005aa1  jmp     loc_180005B69
0x180005aa6  mov     qword ptr [r14], 0
0x180005aad  xor     ebx, ebx
0x180005aaf  mov     rcx, cs:off_180010160
0x180005ab6  mov     r9, cs:off_180010168
0x180005abd  jmp     short loc_180005AF6
0x180005abf  mov     rsi, [rcx]
0x180005ac2  test    rsi, rsi
0x180005ac5  jz      short loc_180005AF2
0x180005ac7  cmp     [rsi+10h], rbx
0x180005acb  jz      short loc_180005AF2
0x180005acd  mov     rdx, [rsi]
0x180005ad0  mov     eax, [rdx]
0x180005ad2  cmp     [r8], eax
0x180005ad5  jnz     short loc_180005AF2
0x180005ad7  mov     eax, [rdx+4]
0x180005ada  cmp     [r8+4], eax
0x180005ade  jnz     short loc_180005AF2
0x180005ae0  mov     eax, [rdx+8]
0x180005ae3  cmp     [r8+8], eax
0x180005ae7  jnz     short loc_180005AF2
0x180005ae9  mov     eax, [rdx+0Ch]
0x180005aec  cmp     [r8+0Ch], eax
0x180005af0  jz      short loc_180005AFD
0x180005af2  add     rcx, 8
0x180005af6  cmp     rcx, r9
0x180005af9  jb      short loc_180005ABF
0x180005afb  jmp     short loc_180005B59
0x180005afd  lea     rdi, [rsi+20h]
0x180005b01  cmp     [rdi], rbx
0x180005b04  jnz     short loc_180005B3E
0x180005b06  lea     rcx, CriticalSection; lpCriticalSection
0x180005b0d  call    cs:__imp_EnterCriticalSection
0x180005b13  cmp     [rdi], rbx
0x180005b16  jnz     short loc_180005B31
0x180005b18  mov     rcx, [rsi+18h]
0x180005b1c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180005b23  mov     rax, [rsi+10h]
0x180005b27  mov     r8, rdi
0x180005b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b2f  mov     ebx, eax
0x180005b31  lea     rcx, CriticalSection; lpCriticalSection
0x180005b38  call    cs:__imp_LeaveCriticalSection
0x180005b3e  mov     rcx, [rdi]
0x180005b41  test    rcx, rcx
0x180005b44  jz      short loc_180005B59
0x180005b46  mov     rax, [rcx]
0x180005b49  mov     r8, r14
0x180005b4c  mov     rdx, rbp
0x180005b4f  mov     rax, [rax]
0x180005b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b57  mov     ebx, eax
0x180005b59  cmp     qword ptr [r14], 0
0x180005b5d  jnz     short loc_180005B69
0x180005b5f  test    ebx, ebx
0x180005b61  mov     eax, 80040111h
0x180005b66  cmovz   ebx, eax
0x180005b69  mov     eax, ebx
0x180005b6b  add     rsp, 20h
0x180005b6f  pop     r14
0x180005b71  pop     rdi
0x180005b72  pop     rsi
0x180005b73  pop     rbp
0x180005b74  pop     rbx
0x180005b75  retn
```
