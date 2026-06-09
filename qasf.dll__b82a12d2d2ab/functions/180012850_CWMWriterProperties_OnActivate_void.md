# CWMWriterProperties::OnActivate(void)

- ea: `0x180012850`
- end: `0x1800128db`
- name: `?OnActivate@CWMWriterProperties@@EEAAJXZ`
- size: `139`
- prototype: `__int64 __fastcall(CWMWriterProperties *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001460`
- `0x180012514`
- `0x180012850`
- `0x18001f010`

## import_xrefs

- `USER32!SendMessageW` at `0x1800128c0`
- `USER32!SendMessageW` at `0x1800128c0`

## pseudocode

```c
__int64 __fastcall CWMWriterProperties::OnActivate(CWMWriterProperties *this)
{
  __int64 v2; // rcx
  CWMWriterProperties *v3; // rcx
  WPARAM wParam[2]; // [rsp+20h] [rbp-48h] BYREF
  struct _GUID v6; // [rsp+30h] [rbp-38h] BYREF
  struct _GUID v7; // [rsp+40h] [rbp-28h] BYREF

  LODWORD(wParam[0]) = 0;
  v2 = *((_QWORD *)this + 12);
  v7 = 0;
  if ( (*(int (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v2 + 48LL))(v2, &v7) >= 0 )
  {
    v6 = v7;
    if ( (int)CWMWriterProperties::GetProfileIndexFromGuid(v3, (unsigned int *)wParam, &v6) >= 0 )
      SendMessageW(*((HWND *)this + 9), 0x14Eu, LODWORD(wParam[0]), 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180012850  push    rbx
0x180012852  sub     rsp, 60h
0x180012856  mov     rax, cs:__security_cookie
0x18001285d  xor     rax, rsp
0x180012860  mov     [rsp+68h+var_18], rax
0x180012865  mov     rbx, rcx
0x180012868  mov     dword ptr [rsp+68h+wParam], 0
0x180012870  mov     rcx, [rcx+60h]
0x180012874  lea     rdx, [rsp+68h+var_28]
0x180012879  xorps   xmm0, xmm0
0x18001287c  movups  [rsp+68h+var_28], xmm0
0x180012881  mov     rax, [rcx]
0x180012884  mov     rax, [rax+30h]
0x180012888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001288d  test    eax, eax
0x18001288f  js      short loc_1800128C6
0x180012891  movaps  xmm0, [rsp+68h+var_28]
0x180012896  lea     r8, [rsp+68h+var_38]; struct _GUID
0x18001289b  lea     rdx, [rsp+68h+wParam]; unsigned int *
0x1800128a0  movdqa  xmmword ptr [rsp+68h+var_38.Data1], xmm0
0x1800128a6  call    ?GetProfileIndexFromGuid@CWMWriterProperties@@AEAAJPEAKU_GUID@@@Z; CWMWriterProperties::GetProfileIndexFromGuid(ulong *,_GUID)
0x1800128ab  test    eax, eax
0x1800128ad  js      short loc_1800128C6
0x1800128af  mov     r8d, dword ptr [rsp+68h+wParam]; wParam
0x1800128b4  xor     r9d, r9d; lParam
0x1800128b7  mov     rcx, [rbx+48h]; hWnd
0x1800128bb  mov     edx, 14Eh; Msg
0x1800128c0  call    cs:__imp_SendMessageW
0x1800128c6  xor     eax, eax
0x1800128c8  mov     rcx, [rsp+68h+var_18]
0x1800128cd  xor     rcx, rsp; StackCookie
0x1800128d0  call    __security_check_cookie
0x1800128d5  add     rsp, 60h
0x1800128d9  pop     rbx
0x1800128da  retn
```
