# DllGetClassObject

- ea: `0x180007660`
- end: `0x180007766`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007660`
- `0x180021010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800076fd`
- `KERNEL32!EnterCriticalSection` at `0x1800076fd`
- `KERNEL32!LeaveCriticalSection` at `0x180007728`
- `KERNEL32!LeaveCriticalSection` at `0x180007728`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v7; // rcx
  __int64 *v8; // r9
  struct ATL::_ATL_OBJMAP_ENTRY30 *v9; // rsi
  _DWORD *v10; // rdx
  _QWORD *v11; // rdi

  if ( !ATL::_AtlComModule )
    return -2147418113;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = 0;
  v7 = off_18002F450;
  v8 = off_18002F458;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_18002F458 )
  {
    v9 = *v7;
    if ( *v7 )
    {
      if ( *((_QWORD *)v9 + 2) )
      {
        v10 = *(_DWORD **)v9;
        if ( rclsid->Data1 == **(_DWORD **)v9
          && *(_DWORD *)&rclsid->Data2 == v10[1]
          && *(_DWORD *)rclsid->Data4 == v10[2]
          && *(_DWORD *)&rclsid->Data4[4] == v10[3] )
        {
          v11 = (_QWORD *)((char *)v9 + 32);
          if ( !*((_QWORD *)v9 + 4) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v11 )
              v6 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v9 + 2))(
                     *((_QWORD *)v9 + 3),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     (__int64)v9 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          if ( *v11 )
            v6 = (**(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *, __int64 *))*v11)(*v11, riid, ppv, v8);
          break;
        }
      }
    }
    ++v7;
  }
  if ( !*ppv && !v6 )
    return -2147221231;
  return v6;
}

```

## disassembly

```asm
0x180007660  push    rbx
0x180007662  push    rbp
0x180007663  push    rsi
0x180007664  push    rdi
0x180007665  push    r14
0x180007667  sub     rsp, 20h
0x18000766b  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180007672  mov     r14, r8
0x180007675  mov     r8, rcx
0x180007678  mov     rbp, rdx
0x18000767b  jnz     short loc_180007687
0x18000767d  mov     ebx, 8000FFFFh
0x180007682  jmp     loc_180007759
0x180007687  test    r14, r14
0x18000768a  jnz     short loc_180007696
0x18000768c  mov     ebx, 80004003h
0x180007691  jmp     loc_180007759
0x180007696  mov     qword ptr [r14], 0
0x18000769d  xor     ebx, ebx
0x18000769f  mov     rcx, cs:off_18002F450
0x1800076a6  mov     r9, cs:off_18002F458
0x1800076ad  jmp     short loc_1800076E6
0x1800076af  mov     rsi, [rcx]
0x1800076b2  test    rsi, rsi
0x1800076b5  jz      short loc_1800076E2
0x1800076b7  cmp     [rsi+10h], rbx
0x1800076bb  jz      short loc_1800076E2
0x1800076bd  mov     rdx, [rsi]
0x1800076c0  mov     eax, [rdx]
0x1800076c2  cmp     [r8], eax
0x1800076c5  jnz     short loc_1800076E2
0x1800076c7  mov     eax, [rdx+4]
0x1800076ca  cmp     [r8+4], eax
0x1800076ce  jnz     short loc_1800076E2
0x1800076d0  mov     eax, [rdx+8]
0x1800076d3  cmp     [r8+8], eax
0x1800076d7  jnz     short loc_1800076E2
0x1800076d9  mov     eax, [rdx+0Ch]
0x1800076dc  cmp     [r8+0Ch], eax
0x1800076e0  jz      short loc_1800076ED
0x1800076e2  add     rcx, 8
0x1800076e6  cmp     rcx, r9
0x1800076e9  jb      short loc_1800076AF
0x1800076eb  jmp     short loc_180007749
0x1800076ed  lea     rdi, [rsi+20h]
0x1800076f1  cmp     [rdi], rbx
0x1800076f4  jnz     short loc_18000772E
0x1800076f6  lea     rcx, CriticalSection; lpCriticalSection
0x1800076fd  call    cs:__imp_EnterCriticalSection
0x180007703  cmp     [rdi], rbx
0x180007706  jnz     short loc_180007721
0x180007708  mov     rcx, [rsi+18h]
0x18000770c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180007713  mov     rax, [rsi+10h]
0x180007717  mov     r8, rdi
0x18000771a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000771f  mov     ebx, eax
0x180007721  lea     rcx, CriticalSection; lpCriticalSection
0x180007728  call    cs:__imp_LeaveCriticalSection
0x18000772e  mov     rcx, [rdi]
0x180007731  test    rcx, rcx
0x180007734  jz      short loc_180007749
0x180007736  mov     rax, [rcx]
0x180007739  mov     r8, r14
0x18000773c  mov     rdx, rbp
0x18000773f  mov     rax, [rax]
0x180007742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007747  mov     ebx, eax
0x180007749  cmp     qword ptr [r14], 0
0x18000774d  jnz     short loc_180007759
0x18000774f  test    ebx, ebx
0x180007751  mov     eax, 80040111h
0x180007756  cmovz   ebx, eax
0x180007759  mov     eax, ebx
0x18000775b  add     rsp, 20h
0x18000775f  pop     r14
0x180007761  pop     rdi
0x180007762  pop     rsi
0x180007763  pop     rbp
0x180007764  pop     rbx
0x180007765  retn
```
