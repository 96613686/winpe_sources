# CSharePagePerm::_StartBackgroundNameResolution(void)

- ea: `0x18006c9c4`
- end: `0x18006caf1`
- name: `?_StartBackgroundNameResolution@CSharePagePerm@@AEAAXXZ`
- size: `301`
- prototype: `void __fastcall(CSharePagePerm *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18006b930`

## callees

- `0x1800098dc`
- `0x18000f720`
- `0x180025504`
- `0x1800259bc`
- `0x18006aa98`
- `0x18006b060`
- `0x18006c9c4`
- `0x18006cb84`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cac9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cac9`
- `SHCORE!SHStrDupW` at `0x18006ca3c`
- `SHCORE!SHStrDupW` at `0x18006ca3c`
- `SHCORE!SHCreateThread` at `0x18006ca95`
- `SHCORE!SHCreateThread` at `0x18006ca95`
- `USER32!SendMessageW` at `0x18006ca00`
- `USER32!SendMessageW` at `0x18006ca00`

## pseudocode

```c
void __fastcall CSharePagePerm::_StartBackgroundNameResolution(HDPA *this)
{
  HWND v2; // rcx
  INT_PTR v3; // rdx
  const WCHAR *v4; // rcx
  const WCHAR **Ptr; // rax
  HRESULT UserNameComboText; // eax
  HDPA **v7; // rax
  HDPA **v8; // rdi
  LPWSTR ppwsz; // [rsp+30h] [rbp+8h] BYREF

  CSharePagePerm::_EnablePage((CSharePagePerm *)this, 0);
  CSharePagePerm::_WaitCursor((CSharePagePerm *)this, 1);
  v2 = (HWND)this[32];
  ppwsz = 0;
  v3 = (int)SendMessageW(v2, 0x147u, 0, 0);
  if ( v3 == -1 || v3 != *((_DWORD *)this + 15) )
  {
    Ptr = (const WCHAR **)DPA_GetPtr(this[30], v3);
    if ( !Ptr )
    {
      UserNameComboText = CSharePagePerm::_GetUserNameComboText((CSharePagePerm *)this, &ppwsz);
      goto LABEL_8;
    }
    v4 = *Ptr;
  }
  else
  {
    v4 = (const WCHAR *)(this + 9);
  }
  UserNameComboText = SHStrDupW(v4, &ppwsz);
LABEL_8:
  if ( UserNameComboText < 0 )
    goto LABEL_13;
  v7 = (HDPA **)operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v7;
  if ( !v7 )
    goto LABEL_13;
  v7[1] = (HDPA *)ppwsz;
  *v7 = this;
  (*((void (__fastcall **)(HDPA *))*this + 1))(this);
  if ( !SHCreateThread(CSharePagePerm::ResolveNameThreadProc, v8, 9u, 0) && (int)ResultFromKnownLastError() < 0 )
  {
    operator delete(v8, (const struct std::nothrow_t *)0x10);
    (*((void (__fastcall **)(HDPA *))*this + 2))(this);
LABEL_13:
    CoTaskMemFree(ppwsz);
    CSharePagePerm::_WaitCursor((CSharePagePerm *)this, 0);
    CSharePagePerm::_EnablePage((CSharePagePerm *)this, 1);
  }
}

```

## disassembly

```asm
0x18006c9c4  mov     [rsp+arg_8], rbx
0x18006c9c9  push    rdi
0x18006c9ca  sub     rsp, 20h
0x18006c9ce  xor     edx, edx; bEnable
0x18006c9d0  mov     rbx, rcx
0x18006c9d3  call    ?_EnablePage@CSharePagePerm@@AEAAXH@Z; CSharePagePerm::_EnablePage(int)
0x18006c9d8  mov     edx, 1; int
0x18006c9dd  mov     rcx, rbx; this
0x18006c9e0  call    ?_WaitCursor@CSharePagePerm@@AEAAXH@Z; CSharePagePerm::_WaitCursor(int)
0x18006c9e5  mov     rcx, [rbx+100h]; hWnd
0x18006c9ec  xor     r9d, r9d; lParam
0x18006c9ef  xor     r8d, r8d; wParam
0x18006c9f2  mov     [rsp+28h+ppwsz], 0
0x18006c9fb  mov     edx, 147h; Msg
0x18006ca00  call    cs:__imp_SendMessageW
0x18006ca06  movsxd  rdx, eax; i
0x18006ca09  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18006ca0d  jz      short loc_18006CA23
0x18006ca0f  movsxd  rax, dword ptr [rbx+3Ch]
0x18006ca13  cmp     rdx, rax
0x18006ca16  jnz     short loc_18006CA23
0x18006ca18  lea     rcx, [rbx+48h]
0x18006ca1c  lea     rdx, [rsp+28h+ppwsz]
0x18006ca21  jmp     short loc_18006CA3C
0x18006ca23  mov     rcx, [rbx+0F0h]; hdpa
0x18006ca2a  call    DPA_GetPtr
0x18006ca2f  lea     rdx, [rsp+28h+ppwsz]; unsigned __int16 **
0x18006ca34  test    rax, rax
0x18006ca37  jz      short loc_18006CA44
0x18006ca39  mov     rcx, [rax]; psz
0x18006ca3c  call    cs:__imp_SHStrDupW
0x18006ca42  jmp     short loc_18006CA4C
0x18006ca44  mov     rcx, rbx; this
0x18006ca47  call    ?_GetUserNameComboText@CSharePagePerm@@AEAAJPEAPEAG@Z; CSharePagePerm::_GetUserNameComboText(ushort * *)
0x18006ca4c  test    eax, eax
0x18006ca4e  js      short loc_18006CAC4
0x18006ca50  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006ca57  mov     ecx, 10h; unsigned __int64
0x18006ca5c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006ca61  mov     rdi, rax
0x18006ca64  test    rax, rax
0x18006ca67  jz      short loc_18006CAC4
0x18006ca69  mov     rcx, [rsp+28h+ppwsz]
0x18006ca6e  mov     [rax+8], rcx
0x18006ca72  mov     [rax], rbx
0x18006ca75  mov     rcx, [rbx]
0x18006ca78  mov     rax, [rcx+8]
0x18006ca7c  mov     rcx, rbx
0x18006ca7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca84  xor     r9d, r9d; pfnCallback
0x18006ca87  lea     rcx, ?ResolveNameThreadProc@CSharePagePerm@@SAKPEAX@Z; pfnThreadProc
0x18006ca8e  mov     rdx, rdi; pData
0x18006ca91  lea     r8d, [r9+9]; flags
0x18006ca95  call    cs:__imp_SHCreateThread
0x18006ca9b  test    eax, eax
0x18006ca9d  jnz     short loc_18006CAE6
0x18006ca9f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006caa4  test    eax, eax
0x18006caa6  jns     short loc_18006CAE6
0x18006caa8  mov     edx, 10h; struct std::nothrow_t *
0x18006caad  mov     rcx, rdi; void *
0x18006cab0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006cab5  mov     rax, [rbx]
0x18006cab8  mov     rcx, rbx
0x18006cabb  mov     rax, [rax+10h]
0x18006cabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cac4  mov     rcx, [rsp+28h+ppwsz]; pv
0x18006cac9  call    cs:__imp_CoTaskMemFree
0x18006cacf  xor     edx, edx; int
0x18006cad1  mov     rcx, rbx; this
0x18006cad4  call    ?_WaitCursor@CSharePagePerm@@AEAAXH@Z; CSharePagePerm::_WaitCursor(int)
0x18006cad9  mov     edx, 1; bEnable
0x18006cade  mov     rcx, rbx; this
0x18006cae1  call    ?_EnablePage@CSharePagePerm@@AEAAXH@Z; CSharePagePerm::_EnablePage(int)
0x18006cae6  mov     rbx, [rsp+28h+arg_8]
0x18006caeb  add     rsp, 20h
0x18006caef  pop     rdi
0x18006caf0  retn
```
