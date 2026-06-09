# CTextMsgFilter::OnKillFocus(void)

- ea: `0x1800539fc`
- end: `0x180053af9`
- name: `?OnKillFocus@CTextMsgFilter@@AEAAXXZ`
- size: `253`
- prototype: `void __fastcall(CTextMsgFilter *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180036920`

## callees

- `0x18001c118`
- `0x1800499e4`
- `0x1800539fc`
- `0x180091158`
- `0x1800911e0`
- `0x180091418`
- `0x180092fb0`
- `0x180095010`

## string_xrefs

- `0x180053a85`: `ImmGetOpenStatus`

## pseudocode

```c
void __fastcall CTextMsgFilter::OnKillFocus(CTextMsgFilter *this)
{
  HKL KeyboardLayout; // rax
  unsigned int Context; // edi
  unsigned __int16 v4; // dx
  __int64 (__fastcall *v5)(_QWORD); // rax
  unsigned int v6; // ecx

  if ( *((_QWORD *)this + 2) )
  {
    if ( (*((_WORD *)this + 16) & 0x400) != 0 )
    {
      KeyboardLayout = CW32System::GetKeyboardLayout(0xFFFFFFFF);
      *((_QWORD *)this + 6) = KeyboardLayout;
      if ( CW32System::IsFELCID((unsigned __int16)KeyboardLayout) )
      {
        Context = CW32System::ImmGetContext(*((HWND *)this + 2));
        if ( Context )
        {
          if ( (*((_BYTE *)this + 32) & 0x40) != 0 )
          {
            v4 = (*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800A7598 + 264LL))(
                   qword_1800A7598,
                   Context) == 0;
          }
          else
          {
            v5 = (__int64 (__fastcall *)(_QWORD))qword_1800A7240;
            if ( !qword_1800A7240 )
            {
              SetIMEProcAddr((FARPROC *)&qword_1800A7240, 0, "ImmGetOpenStatus");
              v5 = (__int64 (__fastcall *)(_QWORD))qword_1800A7240;
            }
            v4 = v5(Context);
          }
          v6 = v4;
          LOWORD(v6) = *((_WORD *)this + 16) ^ (*((_WORD *)this + 16) ^ (v4 << 11)) & 0x800;
          *((_WORD *)this + 16) = v6;
          if ( (v4 & 1) != 0 )
            CW32System::ImmGetConversionStatus(
              Context,
              (unsigned int *)this + 9,
              (unsigned int *)this + 10,
              (v6 >> 6) & 1);
          CW32System::ImmReleaseContext(*((HWND *)this + 2), Context);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800539fc  mov     [rsp+arg_0], rbx
0x180053a01  push    rdi
0x180053a02  sub     rsp, 20h
0x180053a06  cmp     qword ptr [rcx+10h], 0
0x180053a0b  mov     rbx, rcx
0x180053a0e  jz      loc_180053AED
0x180053a14  mov     eax, 400h
0x180053a19  test    [rcx+20h], ax
0x180053a1d  jz      loc_180053AED
0x180053a23  or      ecx, 0FFFFFFFFh; unsigned int
0x180053a26  call    ?GetKeyboardLayout@CW32System@@SAPEAUHKL__@@K@Z; CW32System::GetKeyboardLayout(ulong)
0x180053a2b  movzx   ecx, ax; unsigned int
0x180053a2e  mov     [rbx+30h], rax
0x180053a32  call    ?IsFELCID@CW32System@@SA_NK@Z; CW32System::IsFELCID(ulong)
0x180053a37  test    al, al
0x180053a39  jz      loc_180053AED
0x180053a3f  mov     rcx, [rbx+10h]; HWND
0x180053a43  call    ?ImmGetContext@CW32System@@SAKPEAUHWND__@@@Z; CW32System::ImmGetContext(HWND__ *)
0x180053a48  mov     edi, eax
0x180053a4a  test    eax, eax
0x180053a4c  jz      loc_180053AED
0x180053a52  test    byte ptr [rbx+20h], 40h
0x180053a56  jz      short loc_180053A79
0x180053a58  mov     rcx, cs:qword_1800A7598
0x180053a5f  mov     rdx, [rcx]
0x180053a62  mov     rax, [rdx+108h]
0x180053a69  mov     edx, edi
0x180053a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a70  xor     edx, edx
0x180053a72  test    eax, eax
0x180053a74  setz    dl
0x180053a77  jmp     short loc_180053AAA
0x180053a79  mov     rax, cs:qword_1800A7240
0x180053a80  test    rax, rax
0x180053a83  jnz     short loc_180053AA1
0x180053a85  lea     r8, aImmgetopenstat; "ImmGetOpenStatus"
0x180053a8c  xor     edx, edx
0x180053a8e  lea     rcx, qword_1800A7240
0x180053a95  call    SetIMEProcAddr
0x180053a9a  mov     rax, cs:qword_1800A7240
0x180053aa1  mov     ecx, edi
0x180053aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053aa8  mov     edx, eax
0x180053aaa  movzx   ecx, dx
0x180053aad  mov     eax, 800h
0x180053ab2  shl     cx, 0Bh
0x180053ab6  xor     cx, [rbx+20h]
0x180053aba  and     cx, ax
0x180053abd  xor     cx, [rbx+20h]
0x180053ac1  mov     [rbx+20h], cx
0x180053ac5  test    dl, 1
0x180053ac8  jz      short loc_180053AE2
0x180053aca  shr     ecx, 6
0x180053acd  lea     r8, [rbx+28h]; unsigned int *
0x180053ad1  and     ecx, 1
0x180053ad4  lea     rdx, [rbx+24h]; unsigned int *
0x180053ad8  mov     r9d, ecx; int
0x180053adb  mov     ecx, edi; unsigned int
0x180053add  call    ?ImmGetConversionStatus@CW32System@@SAHKPEAK0H@Z; CW32System::ImmGetConversionStatus(ulong,ulong *,ulong *,int)
0x180053ae2  mov     rcx, [rbx+10h]; HWND
0x180053ae6  mov     edx, edi; unsigned int
0x180053ae8  call    ?ImmReleaseContext@CW32System@@SAHPEAUHWND__@@K@Z; CW32System::ImmReleaseContext(HWND__ *,ulong)
0x180053aed  mov     rbx, [rsp+28h+arg_0]
0x180053af2  add     rsp, 20h
0x180053af6  pop     rdi
0x180053af7  retn
```
