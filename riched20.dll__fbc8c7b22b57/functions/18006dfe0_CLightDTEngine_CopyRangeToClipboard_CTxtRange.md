# CLightDTEngine::CopyRangeToClipboard(CTxtRange *)

- ea: `0x18006dfe0`
- end: `0x18006e1f1`
- name: `?CopyRangeToClipboard@CLightDTEngine@@QEAAJPEAVCTxtRange@@@Z`
- size: `529`
- prototype: `__int64 __fastcall(CLightDTEngine *__hidden this, struct CTxtRange *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18005cf44`
- `0x180089f00`

## callees

- `0x18003cc90`
- `0x180040b14`
- `0x180041b1c`
- `0x18004a284`
- `0x1800559d8`
- `0x18006dfe0`
- `0x18006f13c`
- `0x180092940`
- `0x180095010`

## import_xrefs

- `USER32!OpenClipboard` at `0x18006e107`
- `USER32!OpenClipboard` at `0x18006e107`
- `USER32!EmptyClipboard` at `0x18006e11b`
- `USER32!EmptyClipboard` at `0x18006e11b`
- `USER32!SetClipboardData` at `0x18006e138`
- `USER32!SetClipboardData` at `0x18006e149`
- `USER32!SetClipboardData` at `0x18006e16d`
- `USER32!SetClipboardData` at `0x18006e182`
- `USER32!SetClipboardData` at `0x18006e193`
- `USER32!SetClipboardData` at `0x18006e1a8`
- `USER32!SetClipboardData` at `0x18006e138`
- `USER32!SetClipboardData` at `0x18006e149`
- `USER32!SetClipboardData` at `0x18006e16d`
- `USER32!SetClipboardData` at `0x18006e182`
- `USER32!SetClipboardData` at `0x18006e193`
- `USER32!SetClipboardData` at `0x18006e1a8`
- `USER32!CloseClipboard` at `0x18006e1b4`
- `USER32!CloseClipboard` at `0x18006e1b4`

## pseudocode

```c
__int64 __fastcall CLightDTEngine::CopyRangeToClipboard(CTxtEdit **this, struct CTxtRange *a2)
{
  CTxtEdit *v2; // r14
  CTxtEdit *v4; // rcx
  struct IRichEditOleCallback *RECallback; // rax
  struct IRichEditOleCallback *v7; // r12
  int v8; // ebx
  CObjectMgr *v10; // r14
  int IndexForCp; // edi
  BOOL v12; // edi
  unsigned int v13; // ebx
  CTxtEdit *v14; // rcx
  CTxtEdit *v15; // rcx
  __int64 v16; // [rsp+70h] [rbp+40h] BYREF
  struct IDataObject *v17; // [rsp+80h] [rbp+50h] BYREF
  HWND hWndNewOwner; // [rsp+88h] [rbp+58h] BYREF

  v2 = *this;
  v4 = *this;
  v17 = 0;
  RECallback = CTxtEdit::GetRECallback(v4);
  v16 = 0;
  v7 = RECallback;
  CTxtRange::GetRange(a2, (int *)&v16, (int *)&v16 + 1);
  v8 = v16;
  if ( (int)v16 >= SHIDWORD(v16) )
    return 0;
  v12 = 0;
  if ( HIDWORD(v16) - (_DWORD)v16 == 1 )
  {
    v10 = (CObjectMgr *)*((_QWORD *)v2 + 17);
    if ( v10 )
    {
      IndexForCp = CObjectMgr::FindIndexForCp(v10, SHIDWORD(v16));
      if ( IndexForCp != (unsigned int)CObjectMgr::FindIndexForCp(v10, v8) )
        v12 = 1;
    }
  }
  if ( v7 )
  {
    v13 = ((__int64 (__fastcall *)(struct IRichEditOleCallback *, __int64 *, __int64, struct IDataObject **))v7->lpVtbl->GetClipboardData)(
            v7,
            &v16,
            2,
            &v17);
    if ( !v13 )
      goto LABEL_13;
  }
  if ( !*((_DWORD *)a2 + 22) )
  {
    CTxtEdit::Beep(*this);
    return 0;
  }
  v13 = CLightDTEngine::RangeToDataObject((CLightDTEngine *)this, a2, 3, &v17);
  if ( !v13 )
  {
LABEL_13:
    if ( v17 )
    {
      v13 = CW32System::OleSetClipboard(v17);
      if ( v13 )
      {
        v14 = *this;
        hWndNewOwner = 0;
        *((_BYTE *)this + 25) = 1;
        if ( !(unsigned int)CTxtEdit::TxGetWindow(v14, &hWndNewOwner) && OpenClipboard(hWndNewOwner) && EmptyClipboard() )
        {
          SetClipboardData((unsigned __int16)xmmword_1800A61F0, 0);
          SetClipboardData(0xDu, 0);
          if ( (*((_DWORD *)*this + 48) & 0xFF8FFEFF) != 0 )
          {
            SetClipboardData((unsigned __int16)g_rgFETC, 0);
            SetClipboardData((unsigned __int16)xmmword_1800A6210, 0);
          }
          SetClipboardData(1u, 0);
          if ( v12 )
            SetClipboardData(8u, 0);
          CloseClipboard();
          v13 = 0;
        }
      }
      v15 = this[2];
      if ( v15 )
        (*(void (__fastcall **)(CTxtEdit *))(*(_QWORD *)v15 + 16LL))(v15);
      this[2] = (CTxtEdit *)v17;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18006dfe0  push    rbp
0x18006dfe2  push    rbx
0x18006dfe3  push    rsi
0x18006dfe4  push    rdi
0x18006dfe5  push    r12
0x18006dfe7  push    r14
0x18006dfe9  push    r15
0x18006dfeb  mov     rbp, rsp
0x18006dfee  sub     rsp, 30h
0x18006dff2  mov     r14, [rcx]
0x18006dff5  mov     rsi, rcx
0x18006dff8  mov     rcx, r14; this
0x18006dffb  mov     [rbp+arg_10], 0
0x18006e003  mov     r15, rdx
0x18006e006  call    ?GetRECallback@CTxtEdit@@QEAAPEAUIRichEditOleCallback@@XZ; CTxtEdit::GetRECallback(void)
0x18006e00b  lea     r8, [rbp+arg_4]; int *
0x18006e00f  mov     qword ptr [rbp+40h], 0
0x18006e017  lea     rdx, [rbp+arg_0]; int *
0x18006e01b  mov     rcx, r15; this
0x18006e01e  mov     r12, rax
0x18006e021  call    ?GetRange@CTxtRange@@QEBAJAEAJ0@Z; CTxtRange::GetRange(long &,long &)
0x18006e026  mov     rbx, qword ptr [rbp+arg_0]
0x18006e02a  mov     edx, [rbp+arg_4]; int
0x18006e02d  cmp     ebx, edx
0x18006e02f  jl      short loc_18006E038
0x18006e031  xor     eax, eax
0x18006e033  jmp     loc_18006E1E1
0x18006e038  mov     eax, edx
0x18006e03a  sub     eax, ebx
0x18006e03c  cmp     eax, 1
0x18006e03f  jnz     short loc_18006E06C
0x18006e041  mov     r14, [r14+88h]
0x18006e048  test    r14, r14
0x18006e04b  jz      short loc_18006E06C
0x18006e04d  mov     rcx, r14; this
0x18006e050  call    ?FindIndexForCp@CObjectMgr@@QEAAJJ@Z; CObjectMgr::FindIndexForCp(long)
0x18006e055  mov     edx, ebx; int
0x18006e057  mov     rcx, r14; this
0x18006e05a  mov     edi, eax
0x18006e05c  call    ?FindIndexForCp@CObjectMgr@@QEAAJJ@Z; CObjectMgr::FindIndexForCp(long)
0x18006e061  cmp     edi, eax
0x18006e063  jz      short loc_18006E06C
0x18006e065  mov     edi, 1
0x18006e06a  jmp     short loc_18006E06E
0x18006e06c  xor     edi, edi
0x18006e06e  test    r12, r12
0x18006e071  jz      short loc_18006E097
0x18006e073  mov     rax, [r12]
0x18006e077  lea     r9, [rbp+arg_10]
0x18006e07b  mov     r8d, 2
0x18006e081  lea     rdx, [rbp+arg_0]
0x18006e085  mov     rcx, r12
0x18006e088  mov     rax, [rax+50h]
0x18006e08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e091  mov     ebx, eax
0x18006e093  test    eax, eax
0x18006e095  jz      short loc_18006E0C7
0x18006e097  cmp     dword ptr [r15+58h], 0
0x18006e09c  jnz     short loc_18006E0A8
0x18006e09e  mov     rcx, [rsi]; this
0x18006e0a1  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x18006e0a6  jmp     short loc_18006E031
0x18006e0a8  lea     r9, [rbp+arg_10]; struct IDataObject **
0x18006e0ac  mov     r8d, 3; int
0x18006e0b2  mov     rdx, r15; struct CTxtRange *
0x18006e0b5  mov     rcx, rsi; this
0x18006e0b8  call    ?RangeToDataObject@CLightDTEngine@@QEAAJPEAVCTxtRange@@JPEAPEAUIDataObject@@@Z; CLightDTEngine::RangeToDataObject(CTxtRange *,long,IDataObject * *)
0x18006e0bd  mov     ebx, eax
0x18006e0bf  test    eax, eax
0x18006e0c1  jnz     loc_18006E1DF
0x18006e0c7  mov     rcx, [rbp+arg_10]; struct IDataObject *
0x18006e0cb  test    rcx, rcx
0x18006e0ce  jz      loc_18006E1DF
0x18006e0d4  call    ?OleSetClipboard@CW32System@@SAJPEAUIDataObject@@@Z; CW32System::OleSetClipboard(IDataObject *)
0x18006e0d9  mov     ebx, eax
0x18006e0db  test    eax, eax
0x18006e0dd  jz      loc_18006E1C2
0x18006e0e3  mov     rcx, [rsi]; this
0x18006e0e6  lea     rdx, [rbp+hWndNewOwner]; HWND *
0x18006e0ea  mov     [rbp+hWndNewOwner], 0
0x18006e0f2  mov     byte ptr [rsi+19h], 1
0x18006e0f6  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x18006e0fb  test    eax, eax
0x18006e0fd  jnz     loc_18006E1C2
0x18006e103  mov     rcx, [rbp+hWndNewOwner]; hWndNewOwner
0x18006e107  call    cs:__imp_OpenClipboard
0x18006e10e  nop     dword ptr [rax+rax+00h]
0x18006e113  test    eax, eax
0x18006e115  jz      loc_18006E1C2
0x18006e11b  call    cs:__imp_EmptyClipboard
0x18006e122  nop     dword ptr [rax+rax+00h]
0x18006e127  test    eax, eax
0x18006e129  jz      loc_18006E1C2
0x18006e12f  movzx   ecx, word ptr cs:xmmword_1800A61F0; uFormat
0x18006e136  xor     edx, edx; hMem
0x18006e138  call    cs:__imp_SetClipboardData
0x18006e13f  nop     dword ptr [rax+rax+00h]
0x18006e144  xor     edx, edx; hMem
0x18006e146  lea     ecx, [rdx+0Dh]; uFormat
0x18006e149  call    cs:__imp_SetClipboardData
0x18006e150  nop     dword ptr [rax+rax+00h]
0x18006e155  mov     rax, [rsi]
0x18006e158  test    dword ptr [rax+0C0h], 0FF8FFEFFh
0x18006e162  jz      short loc_18006E18E
0x18006e164  movzx   ecx, word ptr cs:?g_rgFETC@@3PAUtagFORMATETC@@A; uFormat
0x18006e16b  xor     edx, edx; hMem
0x18006e16d  call    cs:__imp_SetClipboardData
0x18006e174  nop     dword ptr [rax+rax+00h]
0x18006e179  movzx   ecx, word ptr cs:xmmword_1800A6210; uFormat
0x18006e180  xor     edx, edx; hMem
0x18006e182  call    cs:__imp_SetClipboardData
0x18006e189  nop     dword ptr [rax+rax+00h]
0x18006e18e  xor     edx, edx; hMem
0x18006e190  lea     ecx, [rdx+1]; uFormat
0x18006e193  call    cs:__imp_SetClipboardData
0x18006e19a  nop     dword ptr [rax+rax+00h]
0x18006e19f  test    edi, edi
0x18006e1a1  jz      short loc_18006E1B4
0x18006e1a3  xor     edx, edx; hMem
0x18006e1a5  lea     ecx, [rdx+8]; uFormat
0x18006e1a8  call    cs:__imp_SetClipboardData
0x18006e1af  nop     dword ptr [rax+rax+00h]
0x18006e1b4  call    cs:__imp_CloseClipboard
0x18006e1bb  nop     dword ptr [rax+rax+00h]
0x18006e1c0  xor     ebx, ebx
0x18006e1c2  mov     rcx, [rsi+10h]
0x18006e1c6  test    rcx, rcx
0x18006e1c9  jz      short loc_18006E1D7
0x18006e1cb  mov     rax, [rcx]
0x18006e1ce  mov     rax, [rax+10h]
0x18006e1d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1d7  mov     rax, [rbp+arg_10]
0x18006e1db  mov     [rsi+10h], rax
0x18006e1df  mov     eax, ebx
0x18006e1e1  add     rsp, 30h
0x18006e1e5  pop     r15
0x18006e1e7  pop     r14
0x18006e1e9  pop     r12
0x18006e1eb  pop     rdi
0x18006e1ec  pop     rsi
0x18006e1ed  pop     rbx
0x18006e1ee  pop     rbp
0x18006e1ef  retn
```
