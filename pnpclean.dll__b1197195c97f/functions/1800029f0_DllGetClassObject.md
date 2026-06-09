# DllGetClassObject

- ea: `0x1800029f0`
- end: `0x180002af6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800029f0`
- `0x18000a010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180002a8d`
- `KERNEL32!EnterCriticalSection` at `0x180002a8d`
- `KERNEL32!LeaveCriticalSection` at `0x180002ab8`
- `KERNEL32!LeaveCriticalSection` at `0x180002ab8`

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
  v7 = off_1800100B0;
  v8 = off_1800100B8;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800100B8 )
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
0x1800029f0  push    rbx
0x1800029f2  push    rbp
0x1800029f3  push    rsi
0x1800029f4  push    rdi
0x1800029f5  push    r14
0x1800029f7  sub     rsp, 20h
0x1800029fb  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180002a02  mov     r14, r8
0x180002a05  mov     r8, rcx
0x180002a08  mov     rbp, rdx
0x180002a0b  jnz     short loc_180002A17
0x180002a0d  mov     ebx, 8000FFFFh
0x180002a12  jmp     loc_180002AE9
0x180002a17  test    r14, r14
0x180002a1a  jnz     short loc_180002A26
0x180002a1c  mov     ebx, 80004003h
0x180002a21  jmp     loc_180002AE9
0x180002a26  mov     qword ptr [r14], 0
0x180002a2d  xor     ebx, ebx
0x180002a2f  mov     rcx, cs:off_1800100B0
0x180002a36  mov     r9, cs:off_1800100B8
0x180002a3d  jmp     short loc_180002A76
0x180002a3f  mov     rsi, [rcx]
0x180002a42  test    rsi, rsi
0x180002a45  jz      short loc_180002A72
0x180002a47  cmp     [rsi+10h], rbx
0x180002a4b  jz      short loc_180002A72
0x180002a4d  mov     rdx, [rsi]
0x180002a50  mov     eax, [rdx]
0x180002a52  cmp     [r8], eax
0x180002a55  jnz     short loc_180002A72
0x180002a57  mov     eax, [rdx+4]
0x180002a5a  cmp     [r8+4], eax
0x180002a5e  jnz     short loc_180002A72
0x180002a60  mov     eax, [rdx+8]
0x180002a63  cmp     [r8+8], eax
0x180002a67  jnz     short loc_180002A72
0x180002a69  mov     eax, [rdx+0Ch]
0x180002a6c  cmp     [r8+0Ch], eax
0x180002a70  jz      short loc_180002A7D
0x180002a72  add     rcx, 8
0x180002a76  cmp     rcx, r9
0x180002a79  jb      short loc_180002A3F
0x180002a7b  jmp     short loc_180002AD9
0x180002a7d  lea     rdi, [rsi+20h]
0x180002a81  cmp     [rdi], rbx
0x180002a84  jnz     short loc_180002ABE
0x180002a86  lea     rcx, CriticalSection; lpCriticalSection
0x180002a8d  call    cs:__imp_EnterCriticalSection
0x180002a93  cmp     [rdi], rbx
0x180002a96  jnz     short loc_180002AB1
0x180002a98  mov     rcx, [rsi+18h]
0x180002a9c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180002aa3  mov     rax, [rsi+10h]
0x180002aa7  mov     r8, rdi
0x180002aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aaf  mov     ebx, eax
0x180002ab1  lea     rcx, CriticalSection; lpCriticalSection
0x180002ab8  call    cs:__imp_LeaveCriticalSection
0x180002abe  mov     rcx, [rdi]
0x180002ac1  test    rcx, rcx
0x180002ac4  jz      short loc_180002AD9
0x180002ac6  mov     rax, [rcx]
0x180002ac9  mov     r8, r14
0x180002acc  mov     rdx, rbp
0x180002acf  mov     rax, [rax]
0x180002ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ad7  mov     ebx, eax
0x180002ad9  cmp     qword ptr [r14], 0
0x180002add  jnz     short loc_180002AE9
0x180002adf  test    ebx, ebx
0x180002ae1  mov     eax, 80040111h
0x180002ae6  cmovz   ebx, eax
0x180002ae9  mov     eax, ebx
0x180002aeb  add     rsp, 20h
0x180002aef  pop     r14
0x180002af1  pop     rdi
0x180002af2  pop     rsi
0x180002af3  pop     rbp
0x180002af4  pop     rbx
0x180002af5  retn
```
