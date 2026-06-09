# DllGetClassObject

- ea: `0x1800059a0`
- end: `0x180005aa6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800059a0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005a68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005a68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005a3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005a3d`

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
  v7 = off_18001C710;
  v8 = off_18001C718;
  while ( v7 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_18001C718 )
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
0x1800059a0  push    rbx
0x1800059a2  push    rbp
0x1800059a3  push    rsi
0x1800059a4  push    rdi
0x1800059a5  push    r14
0x1800059a7  sub     rsp, 20h
0x1800059ab  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800059b2  mov     r14, r8
0x1800059b5  mov     r8, rcx
0x1800059b8  mov     rbp, rdx
0x1800059bb  jnz     short loc_1800059C7
0x1800059bd  mov     ebx, 8000FFFFh
0x1800059c2  jmp     loc_180005A99
0x1800059c7  test    r14, r14
0x1800059ca  jnz     short loc_1800059D6
0x1800059cc  mov     ebx, 80004003h
0x1800059d1  jmp     loc_180005A99
0x1800059d6  mov     qword ptr [r14], 0
0x1800059dd  xor     ebx, ebx
0x1800059df  mov     rcx, cs:off_18001C710
0x1800059e6  mov     r9, cs:off_18001C718
0x1800059ed  jmp     short loc_180005A26
0x1800059ef  mov     rsi, [rcx]
0x1800059f2  test    rsi, rsi
0x1800059f5  jz      short loc_180005A22
0x1800059f7  cmp     [rsi+10h], rbx
0x1800059fb  jz      short loc_180005A22
0x1800059fd  mov     rdx, [rsi]
0x180005a00  mov     eax, [rdx]
0x180005a02  cmp     [r8], eax
0x180005a05  jnz     short loc_180005A22
0x180005a07  mov     eax, [rdx+4]
0x180005a0a  cmp     [r8+4], eax
0x180005a0e  jnz     short loc_180005A22
0x180005a10  mov     eax, [rdx+8]
0x180005a13  cmp     [r8+8], eax
0x180005a17  jnz     short loc_180005A22
0x180005a19  mov     eax, [rdx+0Ch]
0x180005a1c  cmp     [r8+0Ch], eax
0x180005a20  jz      short loc_180005A2D
0x180005a22  add     rcx, 8
0x180005a26  cmp     rcx, r9
0x180005a29  jb      short loc_1800059EF
0x180005a2b  jmp     short loc_180005A89
0x180005a2d  lea     rdi, [rsi+20h]
0x180005a31  cmp     [rdi], rbx
0x180005a34  jnz     short loc_180005A6E
0x180005a36  lea     rcx, CriticalSection; lpCriticalSection
0x180005a3d  call    cs:__imp_EnterCriticalSection
0x180005a43  cmp     [rdi], rbx
0x180005a46  jnz     short loc_180005A61
0x180005a48  mov     rcx, [rsi+18h]
0x180005a4c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180005a53  mov     rax, [rsi+10h]
0x180005a57  mov     r8, rdi
0x180005a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a5f  mov     ebx, eax
0x180005a61  lea     rcx, CriticalSection; lpCriticalSection
0x180005a68  call    cs:__imp_LeaveCriticalSection
0x180005a6e  mov     rcx, [rdi]
0x180005a71  test    rcx, rcx
0x180005a74  jz      short loc_180005A89
0x180005a76  mov     rax, [rcx]
0x180005a79  mov     r8, r14
0x180005a7c  mov     rdx, rbp
0x180005a7f  mov     rax, [rax]
0x180005a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a87  mov     ebx, eax
0x180005a89  cmp     qword ptr [r14], 0
0x180005a8d  jnz     short loc_180005A99
0x180005a8f  test    ebx, ebx
0x180005a91  mov     eax, 80040111h
0x180005a96  cmovz   ebx, eax
0x180005a99  mov     eax, ebx
0x180005a9b  add     rsp, 20h
0x180005a9f  pop     r14
0x180005aa1  pop     rdi
0x180005aa2  pop     rsi
0x180005aa3  pop     rbp
0x180005aa4  pop     rbx
0x180005aa5  retn
```
