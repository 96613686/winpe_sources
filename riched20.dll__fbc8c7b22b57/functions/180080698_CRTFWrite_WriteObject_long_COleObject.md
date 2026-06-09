# CRTFWrite::WriteObject(long,COleObject *)

- ea: `0x180080698`
- end: `0x180080a23`
- name: `?WriteObject@CRTFWrite@@AEAAHJPEAVCOleObject@@@Z`
- size: `907`
- prototype: `__int64 __fastcall(CRTFWrite *__hidden this, int, struct COleObject *)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x18001c5e4`

## callees

- `0x18001d3c8`
- `0x18001dae4`
- `0x180039990`
- `0x18003d330`
- `0x18004bac8`
- `0x18005589c`
- `0x18007f990`
- `0x18007fbac`
- `0x18007fe50`
- `0x1800804e4`
- `0x180080698`
- `0x180080a2c`
- `0x180080b00`
- `0x18008fe00`
- `0x180093bca`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!GlobalSize` at `0x180080734`
- `KERNEL32!GlobalSize` at `0x180080734`
- `KERNEL32!GlobalLock` at `0x180080721`
- `KERNEL32!GlobalLock` at `0x180080721`
- `KERNEL32!GlobalUnlock` at `0x1800807af`
- `KERNEL32!GlobalUnlock` at `0x1800809e3`
- `KERNEL32!GlobalUnlock` at `0x1800807af`
- `KERNEL32!GlobalUnlock` at `0x1800809e3`
- `KERNEL32!GlobalHandle` at `0x1800809d1`
- `KERNEL32!GlobalHandle` at `0x1800809d1`

## pseudocode

```c
__int64 __fastcall CRTFWrite::WriteObject(CRTFWrite *this, LONG a2, HGLOBAL *a3)
{
  CRTFWrite *v6; // rcx
  struct _reobject *v7; // rdx
  HGLOBAL v8; // r14
  _DWORD *v9; // rbx
  int v10; // eax
  int v11; // ecx
  __int16 v12; // ax
  struct _reobject *v13; // rdx
  unsigned __int16 *v14; // rbx
  unsigned __int16 *v15; // rbx
  struct _reobject *v16; // rdx
  HGLOBAL v17; // rbx
  _WORD v19[6]; // [rsp+20h] [rbp-89h] BYREF
  int v20; // [rsp+2Ch] [rbp-7Dh]
  int v21; // [rsp+30h] [rbp-79h]
  int v22; // [rsp+34h] [rbp-75h]
  int v23; // [rsp+38h] [rbp-71h]
  int v24; // [rsp+3Ch] [rbp-6Dh]
  __int16 v25; // [rsp+40h] [rbp-69h]
  __int16 v26; // [rsp+42h] [rbp-67h]
  unsigned __int16 *v27; // [rsp+58h] [rbp-51h]
  unsigned __int16 *v28; // [rsp+60h] [rbp-49h]
  HGLOBAL hMem; // [rsp+70h] [rbp-39h]
  int v30; // [rsp+78h] [rbp-31h]
  _reobject v31; // [rsp+80h] [rbp-29h] BYREF

  memset_0(v19, 0, 0x60u);
  memset_0(&v31, 0, sizeof(v31));
  v31.cbStruct = 72;
  v31.cp = a2;
  COleObject::GetObjectData((COleObject *)a3, &v31, 7u);
  CRTFWrite::GetRtfObject(v6, &v31, (struct _rtfobject *)v19);
  v8 = a3[15];
  if ( v8 )
  {
    v9 = a3[17];
    hMem = GlobalLock(a3[15]);
    v10 = GlobalSize(v8);
    v19[0] = 2;
    v30 = v10;
    v21 = (__int16)CW32System::MulDiv(v31.sizel.cx, 72, 127);
    v11 = (__int16)CW32System::MulDiv(v31.sizel.cy, 72, 127);
    v23 = *v9;
    v24 = v9[1];
    v25 = *((_WORD *)v9 + 4);
    v26 = *((_WORD *)v9 + 5);
    v12 = *((_WORD *)v9 + 6);
    v22 = v11;
    v19[4] = v12;
    CRTFWrite::WriteDib(this, v13, (struct _rtfobject *)v19);
    GlobalUnlock(hMem);
    if ( v31.pstg )
      ((void (__fastcall *)(LPSTORAGE))v31.pstg->lpVtbl->Release)(v31.pstg);
    if ( v31.polesite )
      ((void (__fastcall *)(LPOLECLIENTSITE))v31.polesite->lpVtbl->Release)(v31.polesite);
    if ( v31.poleobj )
      ((void (__fastcall *)(LPOLEOBJECT))v31.poleobj->lpVtbl->Release)(v31.poleobj);
  }
  else
  {
    if ( v19[0] && (unsigned int)(v19[0] - 1) >= 2 )
    {
      CRTFWrite::PutCtrlWord(this, 2, 134, 0);
      CRTFWrite::PutCtrlWord(this, 0, *((unsigned __int16 *)qword_18009CF08 + v19[0]), 0);
      v14 = v27;
      if ( v27 )
      {
        CRTFWrite::PutCtrlWord(this, 3, 128, 0);
        CRTFWrite::WritePcData(this, v14, 0, 0);
        CRTFWrite::PutChar(this, 125);
      }
      v15 = v28;
      if ( v28 )
      {
        CRTFWrite::PutCtrlWord(this, 3, 139, 0);
        CRTFWrite::WritePcData(this, v15, 0, 0);
        CRTFWrite::PutChar(this, 125);
      }
      if ( v20 )
        CRTFWrite::PutCtrlWord(this, 0, 143, 0);
      CRTFWrite::WriteRtfObject(this, (struct _rtfobject *)v19, 0);
      CRTFWrite::PutCtrlWord(this, 3, 133, 0);
      CRTFWrite::Puts(this, qword_18009CF28, 2);
      if ( (unsigned int)CRTFWrite::ObjectWriteToEditstream(this, &v31, (struct _rtfobject *)v19) )
      {
        CRTFWrite::PutChar(this, 125);
        CRTFWrite::PutCtrlWord(this, 2, 188, 0);
        CRTFWrite::WritePicture(this, v16, (struct _rtfobject *)v19);
      }
      else if ( !*((_DWORD *)this + 12) )
      {
        *((_DWORD *)this + 12) = 19;
      }
      CRTFWrite::PutChar(this, 125);
      CRTFWrite::PutChar(this, 125);
    }
    else
    {
      CRTFWrite::WritePicture(this, v7, (struct _rtfobject *)v19);
    }
    if ( v31.pstg )
      ((void (__fastcall *)(LPSTORAGE))v31.pstg->lpVtbl->Release)(v31.pstg);
    if ( v31.polesite )
      ((void (__fastcall *)(LPOLECLIENTSITE))v31.polesite->lpVtbl->Release)(v31.polesite);
    if ( v31.poleobj )
      ((void (__fastcall *)(LPOLEOBJECT))v31.poleobj->lpVtbl->Release)(v31.poleobj);
    if ( hMem )
    {
      v17 = GlobalHandle(hMem);
      GlobalUnlock(v17);
      CW32System::GlobalFree(v17);
    }
    if ( v27 )
      CW32System::CoTaskMemFree(v27);
  }
  return *((unsigned int *)this + 12);
}

```

## disassembly

```asm
0x180080698  push    rbp
0x18008069a  push    rbx
0x18008069b  push    rsi
0x18008069c  push    rdi
0x18008069d  push    r14
0x18008069f  lea     rbp, [rsp-37h]
0x1800806a4  sub     rsp, 0E0h
0x1800806ab  mov     rax, cs:__security_cookie
0x1800806b2  xor     rax, rsp
0x1800806b5  mov     [rbp+57h+var_30], rax
0x1800806b9  mov     ebx, edx
0x1800806bb  mov     rsi, r8
0x1800806be  xor     edx, edx; Val
0x1800806c0  mov     rdi, rcx
0x1800806c3  lea     rcx, [rsp+100h+var_E0]; void *
0x1800806c8  lea     r8d, [rdx+60h]; Size
0x1800806cc  call    memset_0
0x1800806d1  xor     edx, edx; Val
0x1800806d3  lea     rcx, [rbp+57h+var_80]; void *
0x1800806d7  lea     r8d, [rdx+48h]; Size
0x1800806db  call    memset_0
0x1800806e0  mov     r8d, 7; unsigned int
0x1800806e6  mov     [rbp+57h+var_80.cbStruct], 48h ; 'H'
0x1800806ed  lea     rdx, [rbp+57h+var_80]; struct _reobject *
0x1800806f1  mov     [rbp+57h+var_80.cp], ebx
0x1800806f4  mov     rcx, rsi; this
0x1800806f7  call    ?GetObjectData@COleObject@@QEAAJPEAU_reobject@@K@Z; COleObject::GetObjectData(_reobject *,ulong)
0x1800806fc  lea     r8, [rsp+100h+var_E0]; struct _rtfobject *
0x180080701  lea     rdx, [rbp+57h+var_80]; struct _reobject *
0x180080705  call    ?GetRtfObject@CRTFWrite@@AEAAHAEAU_reobject@@AEAU_rtfobject@@@Z; CRTFWrite::GetRtfObject(_reobject &,_rtfobject &)
0x18008070a  mov     r14, [rsi+78h]
0x18008070e  test    r14, r14
0x180080711  jz      loc_180080803
0x180080717  mov     rbx, [rsi+88h]
0x18008071e  mov     rcx, r14; hMem
0x180080721  call    cs:__imp_GlobalLock
0x180080728  nop     dword ptr [rax+rax+00h]
0x18008072d  mov     rcx, r14; hMem
0x180080730  mov     [rbp+57h+hMem], rax
0x180080734  call    cs:__imp_GlobalSize
0x18008073b  nop     dword ptr [rax+rax+00h]
0x180080740  mov     ecx, [rbp+57h+var_80.sizel.cx]; int
0x180080743  mov     esi, 2
0x180080748  mov     [rsp+100h+var_E0], si
0x18008074d  mov     esi, 7Fh
0x180080752  mov     r8d, esi; int
0x180080755  mov     [rbp+57h+var_88], eax
0x180080758  lea     edx, [rsi-37h]; int
0x18008075b  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x180080760  movsx   ecx, ax
0x180080763  lea     edx, [rsi-37h]; int
0x180080766  mov     [rbp+57h+var_D0], ecx
0x180080769  mov     r8d, esi; int
0x18008076c  mov     ecx, [rbp+57h+var_80.sizel.cy]; int
0x18008076f  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x180080774  movsx   ecx, ax
0x180080777  lea     r8, [rsp+100h+var_E0]; struct _rtfobject *
0x18008077c  mov     eax, [rbx]
0x18008077e  mov     [rbp+57h+var_C8], eax
0x180080781  mov     eax, [rbx+4]
0x180080784  mov     [rbp+57h+var_C4], eax
0x180080787  movzx   eax, word ptr [rbx+8]
0x18008078b  mov     [rbp+57h+var_C0], ax
0x18008078f  movzx   eax, word ptr [rbx+0Ah]
0x180080793  mov     [rbp+57h+var_BE], ax
0x180080797  movzx   eax, word ptr [rbx+0Ch]
0x18008079b  mov     [rbp+57h+var_CC], ecx
0x18008079e  mov     rcx, rdi; this
0x1800807a1  mov     [rsp+100h+var_D8], ax
0x1800807a6  call    ?WriteDib@CRTFWrite@@AEAAHAEAU_reobject@@AEAU_rtfobject@@@Z; CRTFWrite::WriteDib(_reobject &,_rtfobject &)
0x1800807ab  mov     rcx, [rbp+57h+hMem]; hMem
0x1800807af  call    cs:__imp_GlobalUnlock
0x1800807b6  nop     dword ptr [rax+rax+00h]
0x1800807bb  mov     rcx, [rbp+57h+var_80.pstg]
0x1800807bf  test    rcx, rcx
0x1800807c2  jz      short loc_1800807D0
0x1800807c4  mov     rax, [rcx]
0x1800807c7  mov     rax, [rax+10h]
0x1800807cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800807d0  mov     rcx, [rbp+57h+var_80.polesite]
0x1800807d4  test    rcx, rcx
0x1800807d7  jz      short loc_1800807E5
0x1800807d9  mov     rax, [rcx]
0x1800807dc  mov     rax, [rax+10h]
0x1800807e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800807e5  mov     rcx, [rbp+57h+var_80.poleobj]
0x1800807e9  test    rcx, rcx
0x1800807ec  jz      loc_180080A05
0x1800807f2  mov     rdx, [rcx]
0x1800807f5  mov     rax, [rdx+10h]
0x1800807f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800807fe  jmp     loc_180080A05
0x180080803  movsx   ecx, [rsp+100h+var_E0]
0x180080808  test    ecx, ecx
0x18008080a  jz      loc_18008097C
0x180080810  sub     ecx, 1
0x180080813  jz      loc_18008097C
0x180080819  cmp     ecx, 1
0x18008081c  jz      loc_18008097C
0x180080822  xor     r9d, r9d; int
0x180080825  mov     r8d, 86h; int
0x18008082b  mov     rcx, rdi; this
0x18008082e  lea     esi, [r9+2]
0x180080832  mov     edx, esi; int
0x180080834  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180080839  movsx   rax, [rsp+100h+var_E0]
0x18008083f  lea     rcx, qword_18009CF08
0x180080846  xor     r9d, r9d; int
0x180080849  xor     edx, edx; int
0x18008084b  movzx   r8d, word ptr [rcx+rax*2]; int
0x180080850  mov     rcx, rdi; this
0x180080853  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180080858  mov     rbx, [rbp+57h+var_A8]
0x18008085c  lea     r14d, [rsi+1]
0x180080860  test    rbx, rbx
0x180080863  jz      short loc_180080892
0x180080865  xor     r9d, r9d; int
0x180080868  lea     r8d, [rsi+7Eh]; int
0x18008086c  mov     edx, r14d; int
0x18008086f  mov     rcx, rdi; this
0x180080872  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180080877  xor     r9d, r9d; int
0x18008087a  xor     r8d, r8d; unsigned int
0x18008087d  mov     rdx, rbx; unsigned __int16 *
0x180080880  mov     rcx, rdi; this
0x180080883  call    ?WritePcData@CRTFWrite@@AEAAHPEBGHH@Z; CRTFWrite::WritePcData(ushort const *,int,int)
0x180080888  mov     dl, 7Dh ; '}'; char
0x18008088a  mov     rcx, rdi; this
0x18008088d  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x180080892  mov     rbx, [rbp+57h+var_A0]
0x180080896  test    rbx, rbx
0x180080899  jz      short loc_1800808CA
0x18008089b  xor     r9d, r9d; int
0x18008089e  mov     r8d, 8Bh; int
0x1800808a4  mov     edx, r14d; int
0x1800808a7  mov     rcx, rdi; this
0x1800808aa  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800808af  xor     r9d, r9d; int
0x1800808b2  xor     r8d, r8d; unsigned int
0x1800808b5  mov     rdx, rbx; unsigned __int16 *
0x1800808b8  mov     rcx, rdi; this
0x1800808bb  call    ?WritePcData@CRTFWrite@@AEAAHPEBGHH@Z; CRTFWrite::WritePcData(ushort const *,int,int)
0x1800808c0  mov     dl, 7Dh ; '}'; char
0x1800808c2  mov     rcx, rdi; this
0x1800808c5  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x1800808ca  cmp     [rbp+57h+var_D4], 0
0x1800808ce  jz      short loc_1800808E3
0x1800808d0  xor     r9d, r9d; int
0x1800808d3  xor     edx, edx; int
0x1800808d5  mov     r8d, 8Fh; int
0x1800808db  mov     rcx, rdi; this
0x1800808de  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800808e3  xor     r8d, r8d; int
0x1800808e6  lea     rdx, [rsp+100h+var_E0]; struct _rtfobject *
0x1800808eb  mov     rcx, rdi; this
0x1800808ee  call    ?WriteRtfObject@CRTFWrite@@AEAAHAEAU_rtfobject@@H@Z; CRTFWrite::WriteRtfObject(_rtfobject &,int)
0x1800808f3  xor     r9d, r9d; int
0x1800808f6  mov     r8d, 85h; int
0x1800808fc  mov     edx, r14d; int
0x1800808ff  mov     rcx, rdi; this
0x180080902  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180080907  mov     r8d, esi; int
0x18008090a  lea     rdx, qword_18009CF28; Src
0x180080911  mov     rcx, rdi; this
0x180080914  call    ?Puts@CRTFWrite@@AEAAHPEBDJ@Z; CRTFWrite::Puts(char const *,long)
0x180080919  lea     r8, [rsp+100h+var_E0]; struct _rtfobject *
0x18008091e  mov     rcx, rdi; this
0x180080921  lea     rdx, [rbp+57h+var_80]; struct _reobject *
0x180080925  call    ?ObjectWriteToEditstream@CRTFWrite@@AEAAHAEAU_reobject@@AEAU_rtfobject@@@Z; CRTFWrite::ObjectWriteToEditstream(_reobject &,_rtfobject &)
0x18008092a  test    eax, eax
0x18008092c  jnz     short loc_18008093C
0x18008092e  cmp     [rdi+30h], eax
0x180080931  jnz     short loc_180080966
0x180080933  mov     dword ptr [rdi+30h], 13h
0x18008093a  jmp     short loc_180080966
0x18008093c  mov     dl, 7Dh ; '}'; char
0x18008093e  mov     rcx, rdi; this
0x180080941  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x180080946  xor     r9d, r9d; int
0x180080949  mov     r8d, 0BCh; int
0x18008094f  mov     edx, esi; int
0x180080951  mov     rcx, rdi; this
0x180080954  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180080959  lea     r8, [rsp+100h+var_E0]; struct _rtfobject *
0x18008095e  mov     rcx, rdi; this
0x180080961  call    ?WritePicture@CRTFWrite@@AEAAHAEAU_reobject@@AEAU_rtfobject@@@Z; CRTFWrite::WritePicture(_reobject &,_rtfobject &)
0x180080966  mov     dl, 7Dh ; '}'; char
0x180080968  mov     rcx, rdi; this
0x18008096b  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x180080970  mov     dl, 7Dh ; '}'; char
0x180080972  mov     rcx, rdi; this
0x180080975  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x18008097a  jmp     short loc_180080989
0x18008097c  lea     r8, [rsp+100h+var_E0]; struct _rtfobject *
0x180080981  mov     rcx, rdi; this
0x180080984  call    ?WritePicture@CRTFWrite@@AEAAHAEAU_reobject@@AEAU_rtfobject@@@Z; CRTFWrite::WritePicture(_reobject &,_rtfobject &)
0x180080989  mov     rcx, [rbp+57h+var_80.pstg]
0x18008098d  test    rcx, rcx
0x180080990  jz      short loc_18008099E
0x180080992  mov     rax, [rcx]
0x180080995  mov     rax, [rax+10h]
0x180080999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008099e  mov     rcx, [rbp+57h+var_80.polesite]
0x1800809a2  test    rcx, rcx
0x1800809a5  jz      short loc_1800809B3
0x1800809a7  mov     rax, [rcx]
0x1800809aa  mov     rax, [rax+10h]
0x1800809ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800809b3  mov     rcx, [rbp+57h+var_80.poleobj]
0x1800809b7  test    rcx, rcx
0x1800809ba  jz      short loc_1800809C8
0x1800809bc  mov     rax, [rcx]
0x1800809bf  mov     rax, [rax+10h]
0x1800809c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800809c8  mov     rcx, [rbp+57h+hMem]; pMem
0x1800809cc  test    rcx, rcx
0x1800809cf  jz      short loc_1800809F7
0x1800809d1  call    cs:__imp_GlobalHandle
0x1800809d8  nop     dword ptr [rax+rax+00h]
0x1800809dd  mov     rcx, rax; hMem
0x1800809e0  mov     rbx, rax
0x1800809e3  call    cs:__imp_GlobalUnlock
0x1800809ea  nop     dword ptr [rax+rax+00h]
0x1800809ef  mov     rcx, rbx; void *
0x1800809f2  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x1800809f7  mov     rcx, [rbp+57h+var_A8]; void *
0x1800809fb  test    rcx, rcx
0x1800809fe  jz      short loc_180080A05
0x180080a00  call    ?CoTaskMemFree@CW32System@@SAXPEAX@Z; CW32System::CoTaskMemFree(void *)
0x180080a05  mov     eax, [rdi+30h]
0x180080a08  mov     rcx, [rbp+57h+var_30]
0x180080a0c  xor     rcx, rsp; StackCookie
0x180080a0f  call    __security_check_cookie
0x180080a14  add     rsp, 0E0h
0x180080a1b  pop     r14
0x180080a1d  pop     rdi
0x180080a1e  pop     rsi
0x180080a1f  pop     rbx
0x180080a20  pop     rbp
0x180080a21  retn
```
