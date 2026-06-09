# DllGetClassObject

- ea: `0x1800029b0`
- end: `0x180002ab6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800029b0`
- `0x18000c010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180002a4d`
- `KERNEL32!EnterCriticalSection` at `0x180002a4d`
- `KERNEL32!LeaveCriticalSection` at `0x180002a78`
- `KERNEL32!LeaveCriticalSection` at `0x180002a78`

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
  v7 = off_1800110B0;
  v8 = off_1800110B8;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800110B8 )
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
0x1800029b0  push    rbx
0x1800029b2  push    rbp
0x1800029b3  push    rsi
0x1800029b4  push    rdi
0x1800029b5  push    r14
0x1800029b7  sub     rsp, 20h
0x1800029bb  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800029c2  mov     r14, r8
0x1800029c5  mov     r8, rcx
0x1800029c8  mov     rbp, rdx
0x1800029cb  jnz     short loc_1800029D7
0x1800029cd  mov     ebx, 8000FFFFh
0x1800029d2  jmp     loc_180002AA9
0x1800029d7  test    r14, r14
0x1800029da  jnz     short loc_1800029E6
0x1800029dc  mov     ebx, 80004003h
0x1800029e1  jmp     loc_180002AA9
0x1800029e6  mov     qword ptr [r14], 0
0x1800029ed  xor     ebx, ebx
0x1800029ef  mov     rcx, cs:off_1800110B0
0x1800029f6  mov     r9, cs:off_1800110B8
0x1800029fd  jmp     short loc_180002A36
0x1800029ff  mov     rsi, [rcx]
0x180002a02  test    rsi, rsi
0x180002a05  jz      short loc_180002A32
0x180002a07  cmp     [rsi+10h], rbx
0x180002a0b  jz      short loc_180002A32
0x180002a0d  mov     rdx, [rsi]
0x180002a10  mov     eax, [rdx]
0x180002a12  cmp     [r8], eax
0x180002a15  jnz     short loc_180002A32
0x180002a17  mov     eax, [rdx+4]
0x180002a1a  cmp     [r8+4], eax
0x180002a1e  jnz     short loc_180002A32
0x180002a20  mov     eax, [rdx+8]
0x180002a23  cmp     [r8+8], eax
0x180002a27  jnz     short loc_180002A32
0x180002a29  mov     eax, [rdx+0Ch]
0x180002a2c  cmp     [r8+0Ch], eax
0x180002a30  jz      short loc_180002A3D
0x180002a32  add     rcx, 8
0x180002a36  cmp     rcx, r9
0x180002a39  jb      short loc_1800029FF
0x180002a3b  jmp     short loc_180002A99
0x180002a3d  lea     rdi, [rsi+20h]
0x180002a41  cmp     [rdi], rbx
0x180002a44  jnz     short loc_180002A7E
0x180002a46  lea     rcx, CriticalSection; lpCriticalSection
0x180002a4d  call    cs:__imp_EnterCriticalSection
0x180002a53  cmp     [rdi], rbx
0x180002a56  jnz     short loc_180002A71
0x180002a58  mov     rcx, [rsi+18h]
0x180002a5c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180002a63  mov     rax, [rsi+10h]
0x180002a67  mov     r8, rdi
0x180002a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a6f  mov     ebx, eax
0x180002a71  lea     rcx, CriticalSection; lpCriticalSection
0x180002a78  call    cs:__imp_LeaveCriticalSection
0x180002a7e  mov     rcx, [rdi]
0x180002a81  test    rcx, rcx
0x180002a84  jz      short loc_180002A99
0x180002a86  mov     rax, [rcx]
0x180002a89  mov     r8, r14
0x180002a8c  mov     rdx, rbp
0x180002a8f  mov     rax, [rax]
0x180002a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a97  mov     ebx, eax
0x180002a99  cmp     qword ptr [r14], 0
0x180002a9d  jnz     short loc_180002AA9
0x180002a9f  test    ebx, ebx
0x180002aa1  mov     eax, 80040111h
0x180002aa6  cmovz   ebx, eax
0x180002aa9  mov     eax, ebx
0x180002aab  add     rsp, 20h
0x180002aaf  pop     r14
0x180002ab1  pop     rdi
0x180002ab2  pop     rsi
0x180002ab3  pop     rbp
0x180002ab4  pop     rbx
0x180002ab5  retn
```
