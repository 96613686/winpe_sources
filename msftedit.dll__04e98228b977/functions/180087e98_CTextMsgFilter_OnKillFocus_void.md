# CTextMsgFilter::OnKillFocus(void)

- ea: `0x180087e98`
- end: `0x180087fd4`
- name: `?OnKillFocus@CTextMsgFilter@@AEAAXXZ`
- size: `316`
- prototype: `void __fastcall(CTextMsgFilter *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800880e0`

## callees

- `0x180087e98`
- `0x18008a3dc`
- `0x18013ab38`
- `0x1801480a8`
- `0x18015e538`
- `0x180160d38`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x180087ee5`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x180087ee5`
- `ext-ms-win-imm-l1-1-0!ImmGetOpenStatus` at `0x180087f3f`
- `ext-ms-win-imm-l1-1-0!ImmGetOpenStatus` at `0x180087f3f`

## pseudocode

```c
void __fastcall CTextMsgFilter::OnKillFocus(CTextMsgFilter *this)
{
  __int64 v2; // rax
  HKL KeyboardLayout; // rax
  HIMC ImmContext; // rax
  HIMC v5; // rdi
  int OpenStatus; // ecx
  unsigned int v7; // r9d

  if ( *((int *)this + 7) < 0 && (*((_DWORD *)this + 7) & 0x2000) != 0 )
  {
    v2 = *((_QWORD *)this + 14);
    if ( v2 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(v2 + 192) + 104LL) + 64LL))(
        *(_QWORD *)(*(_QWORD *)(v2 + 192) + 104LL),
        0);
  }
  if ( (*((_DWORD *)this + 7) & 0x400) != 0 )
  {
    KeyboardLayout = GetKeyboardLayout(0);
    *((_QWORD *)this + 6) = KeyboardLayout;
    if ( CW32System::IsFELCID((unsigned int)KeyboardLayout) )
    {
      ImmContext = LocalGetImmContext(this);
      v5 = ImmContext;
      if ( ImmContext )
      {
        if ( (*((_BYTE *)this + 28) & 0x40) != 0 )
          OpenStatus = (*(__int64 (__fastcall **)(void *, HIMC))(*(_QWORD *)qword_1802E41F8 + 264LL))(
                         qword_1802E41F8,
                         ImmContext) == 0;
        else
          OpenStatus = ImmGetOpenStatus(ImmContext);
        v7 = *((_DWORD *)this + 7) ^ (*((_DWORD *)this + 7) ^ (OpenStatus << 11)) & 0x800;
        *((_DWORD *)this + 7) = v7;
        if ( (OpenStatus & 1) != 0 )
          CW32System::ImmGetConversionStatus(v5, (unsigned int *)this + 10, (unsigned int *)this + 11, (v7 >> 6) & 1);
        LocalReleaseImmContext(this, v5);
      }
    }
  }
  if ( (*((_DWORD *)this + 7) & 0x30000) != 0 )
    CTextMsgFilter::SetIMESentenceMode(this, 0, 0);
  if ( CW32System::_pIMEShare )
  {
    (*(void (__fastcall **)(struct CIMEShare *))(*(_QWORD *)CW32System::_pIMEShare + 40LL))(CW32System::_pIMEShare);
    CW32System::_pIMEShare = 0;
  }
}

```

## disassembly

```asm
0x180087e98  mov     [rsp+arg_0], rbx
0x180087e9d  push    rdi
0x180087e9e  sub     rsp, 20h
0x180087ea2  cmp     dword ptr [rcx+1Ch], 0
0x180087ea6  mov     rbx, rcx
0x180087ea9  jge     short loc_180087ED6
0x180087eab  test    dword ptr [rcx+1Ch], 2000h
0x180087eb2  jz      short loc_180087ED6
0x180087eb4  mov     rax, [rcx+70h]
0x180087eb8  test    rax, rax
0x180087ebb  jz      short loc_180087ED6
0x180087ebd  mov     rax, [rax+0C0h]
0x180087ec4  xor     edx, edx
0x180087ec6  mov     rcx, [rax+68h]
0x180087eca  mov     rax, [rcx]
0x180087ecd  mov     rax, [rax+40h]
0x180087ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087ed6  test    dword ptr [rbx+1Ch], 400h
0x180087edd  jz      loc_180087F8F
0x180087ee3  xor     ecx, ecx; idThread
0x180087ee5  call    cs:__imp_GetKeyboardLayout
0x180087eec  nop     dword ptr [rax+rax+00h]
0x180087ef1  mov     ecx, eax; unsigned int
0x180087ef3  mov     [rbx+30h], rax
0x180087ef7  call    ?IsFELCID@CW32System@@SA_NK@Z; CW32System::IsFELCID(ulong)
0x180087efc  test    al, al
0x180087efe  jz      loc_180087F8F
0x180087f04  mov     rcx, rbx; struct CTextMsgFilter *
0x180087f07  call    ?LocalGetImmContext@@YAPEAUHIMC__@@AEAVCTextMsgFilter@@@Z; LocalGetImmContext(CTextMsgFilter &)
0x180087f0c  mov     rdi, rax
0x180087f0f  test    rax, rax
0x180087f12  jz      short loc_180087F8F
0x180087f14  test    byte ptr [rbx+1Ch], 40h
0x180087f18  jz      short loc_180087F3C
0x180087f1a  mov     rcx, cs:qword_1802E41F8
0x180087f21  mov     rdx, [rcx]
0x180087f24  mov     rax, [rdx+108h]
0x180087f2b  mov     rdx, rdi
0x180087f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087f33  xor     ecx, ecx
0x180087f35  test    eax, eax
0x180087f37  setz    cl
0x180087f3a  jmp     short loc_180087F4D
0x180087f3c  mov     rcx, rdi; HIMC
0x180087f3f  call    cs:__imp_ImmGetOpenStatus
0x180087f46  nop     dword ptr [rax+rax+00h]
0x180087f4b  mov     ecx, eax
0x180087f4d  mov     r9d, ecx
0x180087f50  shl     r9d, 0Bh
0x180087f54  xor     r9d, [rbx+1Ch]
0x180087f58  and     r9d, 800h
0x180087f5f  xor     r9d, [rbx+1Ch]
0x180087f63  mov     [rbx+1Ch], r9d
0x180087f67  test    cl, 1
0x180087f6a  jz      short loc_180087F84
0x180087f6c  shr     r9d, 6
0x180087f70  lea     r8, [rbx+2Ch]; unsigned int *
0x180087f74  and     r9d, 1; int
0x180087f78  lea     rdx, [rbx+28h]; unsigned int *
0x180087f7c  mov     rcx, rdi; HIMC
0x180087f7f  call    ?ImmGetConversionStatus@CW32System@@SAHPEAUHIMC__@@PEAK1H@Z; CW32System::ImmGetConversionStatus(HIMC__ *,ulong *,ulong *,int)
0x180087f84  mov     rdx, rdi; HIMC
0x180087f87  mov     rcx, rbx; struct CTextMsgFilter *
0x180087f8a  call    ?LocalReleaseImmContext@@YAXAEAVCTextMsgFilter@@PEAUHIMC__@@@Z; LocalReleaseImmContext(CTextMsgFilter &,HIMC__ *)
0x180087f8f  test    dword ptr [rbx+1Ch], 30000h
0x180087f96  jz      short loc_180087FA5
0x180087f98  xor     r8d, r8d; HKL
0x180087f9b  xor     edx, edx; int
0x180087f9d  mov     rcx, rbx; this
0x180087fa0  call    ?SetIMESentenceMode@CTextMsgFilter@@AEAAXHPEAUHKL__@@@Z; CTextMsgFilter::SetIMESentenceMode(int,HKL__ *)
0x180087fa5  mov     rcx, cs:?_pIMEShare@CW32System@@2PEAVCIMEShare@@EA; CIMEShare * CW32System::_pIMEShare
0x180087fac  test    rcx, rcx
0x180087faf  jz      short loc_180087FC8
0x180087fb1  mov     rax, [rcx]
0x180087fb4  mov     rax, [rax+28h]
0x180087fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087fbd  mov     cs:?_pIMEShare@CW32System@@2PEAVCIMEShare@@EA, 0; CIMEShare * CW32System::_pIMEShare
0x180087fc8  mov     rbx, [rsp+28h+arg_0]
0x180087fcd  add     rsp, 20h
0x180087fd1  pop     rdi
0x180087fd2  retn
```
