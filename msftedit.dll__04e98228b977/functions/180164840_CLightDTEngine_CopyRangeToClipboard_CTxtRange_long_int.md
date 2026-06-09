# CLightDTEngine::CopyRangeToClipboard(CTxtRange *,long,int)

- ea: `0x180164840`
- end: `0x180164aea`
- name: `?CopyRangeToClipboard@CLightDTEngine@@QEAAJPEAVCTxtRange@@JH@Z`
- size: `682`
- prototype: `__int64 __fastcall(CLightDTEngine *__hidden this, struct CTxtRange *, int, int)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180129ac4`
- `0x180164d2c`
- `0x18017883c`

## callees

- `0x1800b26ec`
- `0x1800b2c1c`
- `0x1800cf0c8`
- `0x1800f89bc`
- `0x1801018a8`
- `0x18012c68c`
- `0x180164840`
- `0x180165cb8`
- `0x1801662a8`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x180164a55`
- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x180164a55`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x1801649a4`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x1801649a4`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1801649d1`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1801649e6`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x180164a0e`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x180164a23`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x180164a34`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x180164a49`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1801649d1`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x1801649e6`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x180164a0e`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x180164a23`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x180164a34`
- `ext-ms-win-ntuser-misc-l1-2-0!SetClipboardData` at `0x180164a49`
- `ext-ms-win-ntuser-misc-l1-2-0!EmptyClipboard` at `0x1801649b8`
- `ext-ms-win-ntuser-misc-l1-2-0!EmptyClipboard` at `0x1801649b8`

## pseudocode

```c
__int64 __fastcall CLightDTEngine::CopyRangeToClipboard(CTxtEdit **this, struct CTxtRange *a2, int a3, int a4)
{
  CTxtEdit *v5; // rcx
  struct IRichEditOleCallback *RECallback; // r15
  __int64 v11; // rax
  struct CTxtStory *v12; // rdi
  int IndexForCp; // ebx
  CObjectMgr *v14; // rcx
  BOOL v15; // edi
  unsigned int v16; // ebx
  char v17; // r15
  CTxtEdit *v18; // rcx
  CTxtEdit *v19; // rcx
  HWND hWndNewOwner; // [rsp+30h] [rbp-18h] BYREF
  struct IDataObject *v21[2]; // [rsp+38h] [rbp-10h] BYREF
  __int64 v22; // [rsp+90h] [rbp+48h] BYREF

  v22 = 0;
  v5 = *this;
  v21[0] = 0;
  RECallback = CTxtEdit::GetRECallback(v5);
  CTxtRange::GetRange(a2, (int *)&v22, (int *)&v22 + 1);
  if ( (int)v22 >= SHIDWORD(v22) )
    return 0;
  v15 = 0;
  if ( HIDWORD(v22) - (_DWORD)v22 == 1 )
  {
    if ( (unsigned int)CRchTxtPtr::GetObjectCount((struct CTxtRange *)((char *)a2 + 8)) )
    {
      v11 = *((_QWORD *)a2 + 3);
      v12 = (struct CTxtStory *)((v11 - 8) & -(__int64)(v11 != 0));
      IndexForCp = CObjectMgr::FindIndexForCp((CObjectMgr *)(v11 - 8), SHIDWORD(v22), v12);
      if ( IndexForCp != CObjectMgr::FindIndexForCp(v14, v22, v12) )
        v15 = 1;
    }
  }
  if ( !RECallback
    || (v16 = ((__int64 (__fastcall *)(struct IRichEditOleCallback *, __int64 *, _QWORD, struct IDataObject **))RECallback->lpVtbl->GetClipboardData)(
                RECallback,
                &v22,
                (unsigned int)(a4 != 0) + 2,
                v21)) != 0 )
  {
    if ( !*((_DWORD *)a2 + 26) )
    {
      CTxtEdit::Beep(*this);
      return 0;
    }
    v17 = 0;
    v16 = CLightDTEngine::RangeToDataObject((CLightDTEngine *)this, a2, a3 | 3u, v21);
    if ( v16 )
      return v16;
  }
  else
  {
    v17 = 1;
  }
  if ( v21[0] )
  {
    v16 = (*(__int64 (__fastcall **)(struct IClipboard *, struct IDataObject *, CTxtEdit *))(*(_QWORD *)g_pIClipboard
                                                                                           + 24LL))(
            g_pIClipboard,
            v21[0],
            this[4]);
    if ( v16 )
    {
      v18 = *this;
      hWndNewOwner = 0;
      *((_BYTE *)this + 26) = 1;
      if ( !(unsigned int)CTxtEdit::TxGetWindow(v18, &hWndNewOwner) && OpenClipboard(hWndNewOwner) && EmptyClipboard() )
      {
        SetClipboardData(0xDu, 0);
        SetClipboardData(stru_1802E19E0.cfFormat, 0);
        if ( (*((_QWORD *)*this + 12) & 0xFFFFFFFFFFFBFE3FuLL) != 0 || *((_QWORD *)*this + 13) )
        {
          SetClipboardData(stru_1802E19C0.cfFormat, 0);
          SetClipboardData(stru_1802E1A00.cfFormat, 0);
        }
        SetClipboardData(1u, 0);
        if ( v15 )
          SetClipboardData(8u, 0);
        CloseClipboard();
        v16 = 0;
      }
    }
    v19 = this[2];
    if ( !v19 )
      goto LABEL_33;
    hWndNewOwner = 0;
    if ( (**(unsigned int (__fastcall ***)(CTxtEdit *, GUID *, HWND *))v19)(v19, &IID_IRichEditDO, &hWndNewOwner) )
      hWndNewOwner = 0;
    if ( CLightDTEngine::ReleaseDataObject((CLightDTEngine *)this) > 1 )
    {
      if ( !hWndNewOwner )
      {
LABEL_33:
        this[2] = (CTxtEdit *)v21[0];
        *((_BYTE *)this + 24) = v17;
        return v16;
      }
      (*(void (__fastcall **)(HWND))(*((_QWORD *)hWndNewOwner + 1) + 16LL))(hWndNewOwner + 2);
    }
    if ( hWndNewOwner )
      (*(void (__fastcall **)(HWND))(*(_QWORD *)hWndNewOwner + 16LL))(hWndNewOwner);
    goto LABEL_33;
  }
  return v16;
}

```

## disassembly

```asm
0x180164840  push    rbp
0x180164842  push    rbx
0x180164843  push    rsi
0x180164844  push    rdi
0x180164845  push    r12
0x180164847  push    r13
0x180164849  push    r14
0x18016484b  push    r15
0x18016484d  mov     rbp, rsp
0x180164850  sub     rsp, 48h
0x180164854  mov     rsi, rcx
0x180164857  mov     qword ptr [rbp+arg_0], 0
0x18016485f  mov     rcx, [rcx]; this
0x180164862  mov     r13d, r9d
0x180164865  mov     r12d, r8d
0x180164868  mov     [rbp+var_10], 0
0x180164870  mov     r14, rdx
0x180164873  call    ?GetRECallback@CTxtEdit@@QEAAPEAUIRichEditOleCallback@@XZ; CTxtEdit::GetRECallback(void)
0x180164878  lea     r8, [rbp+arg_4]; int *
0x18016487c  mov     rcx, r14; this
0x18016487f  lea     rdx, [rbp+arg_0]; int *
0x180164883  mov     r15, rax
0x180164886  call    ?GetRange@CTxtRange@@QEBAJAEAJ0@Z; CTxtRange::GetRange(long &,long &)
0x18016488b  mov     ecx, [rbp+arg_4]
0x18016488e  cmp     [rbp+arg_0], ecx
0x180164891  jl      short loc_18016489A
0x180164893  xor     eax, eax
0x180164895  jmp     loc_180164AD8
0x18016489a  sub     ecx, [rbp+arg_0]
0x18016489d  cmp     ecx, 1
0x1801648a0  jnz     short loc_1801648E3
0x1801648a2  lea     rcx, [r14+8]; this
0x1801648a6  call    ?GetObjectCount@CRchTxtPtr@@QEBAJXZ; CRchTxtPtr::GetObjectCount(void)
0x1801648ab  test    eax, eax
0x1801648ad  jz      short loc_1801648E3
0x1801648af  mov     rax, [r14+18h]
0x1801648b3  mov     edx, [rbp+arg_4]; int
0x1801648b6  lea     rcx, [rax-8]; this
0x1801648ba  neg     rax
0x1801648bd  sbb     rdi, rdi
0x1801648c0  and     rdi, rcx
0x1801648c3  mov     r8, rdi; struct CTxtStory *
0x1801648c6  call    ?FindIndexForCp@CObjectMgr@@QEAAJJPEAVCTxtStory@@@Z; CObjectMgr::FindIndexForCp(long,CTxtStory *)
0x1801648cb  mov     edx, [rbp+arg_0]; int
0x1801648ce  mov     r8, rdi; struct CTxtStory *
0x1801648d1  mov     ebx, eax
0x1801648d3  call    ?FindIndexForCp@CObjectMgr@@QEAAJJPEAVCTxtStory@@@Z; CObjectMgr::FindIndexForCp(long,CTxtStory *)
0x1801648d8  cmp     ebx, eax
0x1801648da  jz      short loc_1801648E3
0x1801648dc  mov     edi, 1
0x1801648e1  jmp     short loc_1801648E5
0x1801648e3  xor     edi, edi
0x1801648e5  test    r15, r15
0x1801648e8  jz      short loc_18016491D
0x1801648ea  mov     rax, [r15]
0x1801648ed  lea     r9, [rbp+var_10]
0x1801648f1  neg     r13d
0x1801648f4  lea     rdx, [rbp+arg_0]
0x1801648f8  mov     rcx, r15
0x1801648fb  sbb     r8d, r8d
0x1801648fe  mov     rax, [rax+50h]
0x180164902  neg     r8d
0x180164905  add     r8d, 2
0x180164909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016490e  xor     r13d, r13d
0x180164911  mov     ebx, eax
0x180164913  test    eax, eax
0x180164915  jnz     short loc_180164920
0x180164917  lea     r15d, [rax+1]
0x18016491b  jmp     short loc_180164956
0x18016491d  xor     r13d, r13d
0x180164920  cmp     [r14+68h], r13d
0x180164924  jnz     short loc_180164933
0x180164926  mov     rcx, [rsi]; this
0x180164929  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x18016492e  jmp     loc_180164893
0x180164933  or      r12d, 3
0x180164937  lea     r9, [rbp+var_10]; struct IDataObject **
0x18016493b  mov     r8d, r12d; int
0x18016493e  mov     rdx, r14; struct CTxtRange *
0x180164941  mov     rcx, rsi; this
0x180164944  mov     r15d, r13d
0x180164947  call    ?RangeToDataObject@CLightDTEngine@@QEAAJPEAVCTxtRange@@JPEAPEAUIDataObject@@@Z; CLightDTEngine::RangeToDataObject(CTxtRange *,long,IDataObject * *)
0x18016494c  mov     ebx, eax
0x18016494e  test    eax, eax
0x180164950  jnz     loc_180164AD6
0x180164956  mov     rdx, [rbp+var_10]
0x18016495a  test    rdx, rdx
0x18016495d  jz      loc_180164AD6
0x180164963  mov     rcx, cs:?g_pIClipboard@@3PEAVIClipboard@@EA; IClipboard * g_pIClipboard
0x18016496a  mov     r8, [rsi+20h]
0x18016496e  mov     rax, [rcx]
0x180164971  mov     rax, [rax+18h]
0x180164975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016497a  mov     ebx, eax
0x18016497c  test    eax, eax
0x18016497e  jz      loc_180164A64
0x180164984  mov     rcx, [rsi]; this
0x180164987  lea     rdx, [rbp+hWndNewOwner]; HWND *
0x18016498b  mov     [rbp+hWndNewOwner], r13
0x18016498f  mov     byte ptr [rsi+1Ah], 1
0x180164993  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x180164998  test    eax, eax
0x18016499a  jnz     loc_180164A64
0x1801649a0  mov     rcx, [rbp+hWndNewOwner]; hWndNewOwner
0x1801649a4  call    cs:__imp_OpenClipboard
0x1801649ab  nop     dword ptr [rax+rax+00h]
0x1801649b0  test    eax, eax
0x1801649b2  jz      loc_180164A64
0x1801649b8  call    cs:__imp_EmptyClipboard
0x1801649bf  nop     dword ptr [rax+rax+00h]
0x1801649c4  test    eax, eax
0x1801649c6  jz      loc_180164A64
0x1801649cc  xor     edx, edx; hMem
0x1801649ce  lea     ecx, [rdx+0Dh]; uFormat
0x1801649d1  call    cs:__imp_SetClipboardData
0x1801649d8  nop     dword ptr [rax+rax+00h]
0x1801649dd  movzx   ecx, cs:stru_1802E19E0.cfFormat; uFormat
0x1801649e4  xor     edx, edx; hMem
0x1801649e6  call    cs:__imp_SetClipboardData
0x1801649ed  nop     dword ptr [rax+rax+00h]
0x1801649f2  mov     rax, [rsi]
0x1801649f5  test    qword ptr [rax+60h], 0FFFFFFFFFFFBFE3Fh
0x1801649fd  jnz     short loc_180164A05
0x1801649ff  cmp     [rax+68h], r13
0x180164a03  jz      short loc_180164A2F
0x180164a05  movzx   ecx, cs:stru_1802E19C0.cfFormat; uFormat
0x180164a0c  xor     edx, edx; hMem
0x180164a0e  call    cs:__imp_SetClipboardData
0x180164a15  nop     dword ptr [rax+rax+00h]
0x180164a1a  movzx   ecx, cs:stru_1802E1A00.cfFormat; uFormat
0x180164a21  xor     edx, edx; hMem
0x180164a23  call    cs:__imp_SetClipboardData
0x180164a2a  nop     dword ptr [rax+rax+00h]
0x180164a2f  xor     edx, edx; hMem
0x180164a31  lea     ecx, [rdx+1]; uFormat
0x180164a34  call    cs:__imp_SetClipboardData
0x180164a3b  nop     dword ptr [rax+rax+00h]
0x180164a40  test    edi, edi
0x180164a42  jz      short loc_180164A55
0x180164a44  xor     edx, edx; hMem
0x180164a46  lea     ecx, [rdx+8]; uFormat
0x180164a49  call    cs:__imp_SetClipboardData
0x180164a50  nop     dword ptr [rax+rax+00h]
0x180164a55  call    cs:__imp_CloseClipboard
0x180164a5c  nop     dword ptr [rax+rax+00h]
0x180164a61  mov     ebx, r13d
0x180164a64  mov     rcx, [rsi+10h]
0x180164a68  test    rcx, rcx
0x180164a6b  jz      short loc_180164ACA
0x180164a6d  mov     [rbp+hWndNewOwner], r13
0x180164a71  lea     r8, [rbp+hWndNewOwner]
0x180164a75  mov     rax, [rcx]
0x180164a78  lea     rdx, IID_IRichEditDO
0x180164a7f  mov     rax, [rax]
0x180164a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164a87  test    eax, eax
0x180164a89  jz      short loc_180164A8F
0x180164a8b  mov     [rbp+hWndNewOwner], r13
0x180164a8f  mov     rcx, rsi; this
0x180164a92  call    ?ReleaseDataObject@CLightDTEngine@@AEAAKXZ; CLightDTEngine::ReleaseDataObject(void)
0x180164a97  cmp     eax, 1
0x180164a9a  jbe     short loc_180164AB5
0x180164a9c  mov     rcx, [rbp+hWndNewOwner]
0x180164aa0  test    rcx, rcx
0x180164aa3  jz      short loc_180164ACA
0x180164aa5  add     rcx, 8
0x180164aa9  mov     rax, [rcx]
0x180164aac  mov     rax, [rax+10h]
0x180164ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164ab5  mov     rcx, [rbp+hWndNewOwner]
0x180164ab9  test    rcx, rcx
0x180164abc  jz      short loc_180164ACA
0x180164abe  mov     rax, [rcx]
0x180164ac1  mov     rax, [rax+10h]
0x180164ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164aca  mov     rax, [rbp+var_10]
0x180164ace  mov     [rsi+10h], rax
0x180164ad2  mov     [rsi+18h], r15b
0x180164ad6  mov     eax, ebx
0x180164ad8  add     rsp, 48h
0x180164adc  pop     r15
0x180164ade  pop     r14
0x180164ae0  pop     r13
0x180164ae2  pop     r12
0x180164ae4  pop     rdi
0x180164ae5  pop     rsi
0x180164ae6  pop     rbx
0x180164ae7  pop     rbp
0x180164ae8  retn
```
