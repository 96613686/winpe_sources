# COverlay::NotifyChange(ulong)

- ea: `0x1800a5f78`
- end: `0x1800a6121`
- name: `?NotifyChange@COverlay@@QEAAJK@Z`
- size: `425`
- prototype: `__int64 __fastcall(COverlay *__hidden this, unsigned int)`
- caller_count: `5`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002e610`
- `0x180031884`
- `0x1800a47a0`
- `0x1800a54b0`
- `0x1800a6350`

## callees

- `0x1800388a0`
- `0x1800a5764`
- `0x1800a596c`
- `0x1800a5bb8`
- `0x1800a5f78`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800a60f6`
- `KERNEL32!LeaveCriticalSection` at `0x1800a60f6`
- `KERNEL32!EnterCriticalSection` at `0x1800a5fd7`
- `KERNEL32!EnterCriticalSection` at `0x1800a5fd7`
- `ole32!CoTaskMemFree` at `0x1800a60d8`
- `ole32!CoTaskMemFree` at `0x1800a60e7`
- `ole32!CoTaskMemFree` at `0x1800a60d8`
- `ole32!CoTaskMemFree` at `0x1800a60e7`

## pseudocode

```c
__int64 __fastcall COverlay::NotifyChange(COverlay *this, unsigned __int8 a2)
{
  struct tagPALETTEENTRY *v3; // r14
  struct _RGNDATA *v4; // r15
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  int VideoClipInfo; // eax
  int DisplayPalette; // eax
  unsigned int v10; // [rsp+30h] [rbp-29h] BYREF
  struct _RGNDATA *v11; // [rsp+38h] [rbp-21h] BYREF
  struct tagPALETTEENTRY *v12; // [rsp+40h] [rbp-19h] BYREF
  struct tagRECT v13; // [rsp+48h] [rbp-11h] BYREF
  struct tagRECT v14; // [rsp+58h] [rbp-1h] BYREF
  struct tagCOLORKEY v15; // [rsp+68h] [rbp+Fh] BYREF

  v3 = 0;
  v12 = 0;
  v4 = 0;
  v10 = 0;
  v11 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)(((unsigned __int64)this + 32) & -(__int64)(this != 0));
  v15 = 0;
  v14 = 0;
  v13 = 0;
  EnterCriticalSection(v6);
  if ( *((_QWORD *)this + 14) )
  {
    if ( (a2 & *((_BYTE *)this + 120) & 8) != 0 && COverlay::GetVideoClipInfo(this, &v14, &v13, 0) >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, struct tagRECT *, struct tagRECT *))(**((_QWORD **)this + 14) + 48LL))(
        *((_QWORD *)this + 14),
        &v14,
        &v13);
      *((struct tagRECT *)this + 9) = v13;
    }
    if ( (a2 & *((_BYTE *)this + 120) & 1) != 0 )
    {
      VideoClipInfo = COverlay::GetVideoClipInfo(this, &v14, &v13, &v11);
      v4 = v11;
      if ( VideoClipInfo >= 0 )
        (*(void (__fastcall **)(_QWORD, struct tagRECT *, struct tagRECT *, struct _RGNDATA *))(**((_QWORD **)this + 14)
                                                                                              + 32LL))(
          *((_QWORD *)this + 14),
          &v14,
          &v13,
          v11);
    }
    if ( (a2 & *((_BYTE *)this + 120) & 2) != 0 )
    {
      DisplayPalette = COverlay::GetDisplayPalette(this, &v10, &v12);
      v3 = v12;
      if ( DisplayPalette >= 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD, struct tagPALETTEENTRY *))(**((_QWORD **)this + 14) + 24LL))(
          *((_QWORD *)this + 14),
          v10,
          v12);
    }
    if ( (a2 & *((_BYTE *)this + 120) & 4) != 0 && (int)COverlay::GetWindowColourKey(this, &v15) >= 0 )
      (*(void (__fastcall **)(_QWORD, struct tagCOLORKEY *))(**((_QWORD **)this + 14) + 40LL))(
        *((_QWORD *)this + 14),
        &v15);
    CoTaskMemFree(v4);
    CoTaskMemFree(v3);
  }
  LeaveCriticalSection(v6);
  return 0;
}

```

## disassembly

```asm
0x1800a5f78  push    rbp
0x1800a5f7a  push    rbx
0x1800a5f7b  push    rsi
0x1800a5f7c  push    rdi
0x1800a5f7d  push    r14
0x1800a5f7f  push    r15
0x1800a5f81  lea     rbp, [rsp-2Fh]
0x1800a5f86  sub     rsp, 88h
0x1800a5f8d  mov     rax, cs:__security_cookie
0x1800a5f94  xor     rax, rsp
0x1800a5f97  mov     [rbp+57h+var_38], rax
0x1800a5f9b  mov     rax, rcx
0x1800a5f9e  mov     rbx, rcx
0x1800a5fa1  add     rcx, 20h ; ' '
0x1800a5fa5  xor     r14d, r14d
0x1800a5fa8  xorps   xmm0, xmm0
0x1800a5fab  mov     [rbp+57h+var_70], r14
0x1800a5faf  xor     r15d, r15d
0x1800a5fb2  mov     [rbp+57h+var_80], r14d
0x1800a5fb6  neg     rax
0x1800a5fb9  mov     [rbp+57h+var_78], r15
0x1800a5fbd  xorps   xmm1, xmm1
0x1800a5fc0  mov     edi, edx
0x1800a5fc2  sbb     rsi, rsi
0x1800a5fc5  and     rsi, rcx
0x1800a5fc8  mov     rcx, rsi; lpCriticalSection
0x1800a5fcb  movups  xmmword ptr [rbp+57h+var_48.KeyType], xmm0
0x1800a5fcf  movups  xmmword ptr [rbp+57h+var_58.left], xmm1
0x1800a5fd3  movups  xmmword ptr [rbp+57h+var_68.left], xmm0
0x1800a5fd7  call    cs:__imp_EnterCriticalSection
0x1800a5fde  nop     dword ptr [rax+rax+00h]
0x1800a5fe3  cmp     [rbx+70h], r14
0x1800a5fe7  jz      loc_1800A60F3
0x1800a5fed  mov     eax, [rbx+78h]
0x1800a5ff0  and     eax, edi
0x1800a5ff2  test    al, 8
0x1800a5ff4  jz      short loc_1800A6031
0x1800a5ff6  xor     r9d, r9d; struct _RGNDATA **
0x1800a5ff9  lea     r8, [rbp+57h+var_68]; struct tagRECT *
0x1800a5ffd  lea     rdx, [rbp+57h+var_58]; struct tagRECT *
0x1800a6001  mov     rcx, rbx; this
0x1800a6004  call    ?GetVideoClipInfo@COverlay@@AEAAJPEAUtagRECT@@0PEAPEAU_RGNDATA@@@Z; COverlay::GetVideoClipInfo(tagRECT *,tagRECT *,_RGNDATA * *)
0x1800a6009  test    eax, eax
0x1800a600b  js      short loc_1800A6031
0x1800a600d  mov     rcx, [rbx+70h]
0x1800a6011  lea     r8, [rbp+57h+var_68]
0x1800a6015  lea     rdx, [rbp+57h+var_58]
0x1800a6019  mov     rax, [rcx]
0x1800a601c  mov     rax, [rax+30h]
0x1800a6020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6025  movups  xmm0, xmmword ptr [rbp+57h+var_68.left]
0x1800a6029  movdqu  xmmword ptr [rbx+90h], xmm0
0x1800a6031  mov     eax, [rbx+78h]
0x1800a6034  and     eax, edi
0x1800a6036  test    al, 1
0x1800a6038  jz      short loc_1800A6071
0x1800a603a  lea     r9, [rbp+57h+var_78]; struct _RGNDATA **
0x1800a603e  mov     rcx, rbx; this
0x1800a6041  lea     r8, [rbp+57h+var_68]; struct tagRECT *
0x1800a6045  lea     rdx, [rbp+57h+var_58]; struct tagRECT *
0x1800a6049  call    ?GetVideoClipInfo@COverlay@@AEAAJPEAUtagRECT@@0PEAPEAU_RGNDATA@@@Z; COverlay::GetVideoClipInfo(tagRECT *,tagRECT *,_RGNDATA * *)
0x1800a604e  mov     r15, [rbp+57h+var_78]
0x1800a6052  test    eax, eax
0x1800a6054  js      short loc_1800A6071
0x1800a6056  mov     rcx, [rbx+70h]
0x1800a605a  lea     r8, [rbp+57h+var_68]
0x1800a605e  mov     r9, r15
0x1800a6061  lea     rdx, [rbp+57h+var_58]
0x1800a6065  mov     rax, [rcx]
0x1800a6068  mov     rax, [rax+20h]
0x1800a606c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6071  mov     eax, [rbx+78h]
0x1800a6074  and     eax, edi
0x1800a6076  test    al, 2
0x1800a6078  jz      short loc_1800A60A8
0x1800a607a  lea     r8, [rbp+57h+var_70]; struct tagPALETTEENTRY **
0x1800a607e  mov     rcx, rbx; this
0x1800a6081  lea     rdx, [rbp+57h+var_80]; unsigned int *
0x1800a6085  call    ?GetDisplayPalette@COverlay@@AEAAJPEAKPEAPEAUtagPALETTEENTRY@@@Z; COverlay::GetDisplayPalette(ulong *,tagPALETTEENTRY * *)
0x1800a608a  mov     r14, [rbp+57h+var_70]
0x1800a608e  test    eax, eax
0x1800a6090  js      short loc_1800A60A8
0x1800a6092  mov     rcx, [rbx+70h]
0x1800a6096  mov     r8, r14
0x1800a6099  mov     edx, [rbp+57h+var_80]
0x1800a609c  mov     rax, [rcx]
0x1800a609f  mov     rax, [rax+18h]
0x1800a60a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a60a8  mov     eax, [rbx+78h]
0x1800a60ab  and     eax, edi
0x1800a60ad  test    al, 4
0x1800a60af  jz      short loc_1800A60D5
0x1800a60b1  lea     rdx, [rbp+57h+var_48]; struct tagCOLORKEY *
0x1800a60b5  mov     rcx, rbx; this
0x1800a60b8  call    ?GetWindowColourKey@COverlay@@AEAAJPEAUtagCOLORKEY@@@Z; COverlay::GetWindowColourKey(tagCOLORKEY *)
0x1800a60bd  test    eax, eax
0x1800a60bf  js      short loc_1800A60D5
0x1800a60c1  mov     rcx, [rbx+70h]
0x1800a60c5  lea     rdx, [rbp+57h+var_48]
0x1800a60c9  mov     rax, [rcx]
0x1800a60cc  mov     rax, [rax+28h]
0x1800a60d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a60d5  mov     rcx, r15; pv
0x1800a60d8  call    cs:__imp_CoTaskMemFree
0x1800a60df  nop     dword ptr [rax+rax+00h]
0x1800a60e4  mov     rcx, r14; pv
0x1800a60e7  call    cs:__imp_CoTaskMemFree
0x1800a60ee  nop     dword ptr [rax+rax+00h]
0x1800a60f3  mov     rcx, rsi; lpCriticalSection
0x1800a60f6  call    cs:__imp_LeaveCriticalSection
0x1800a60fd  nop     dword ptr [rax+rax+00h]
0x1800a6102  xor     eax, eax
0x1800a6104  mov     rcx, [rbp+57h+var_38]
0x1800a6108  xor     rcx, rsp; StackCookie
0x1800a610b  call    __security_check_cookie
0x1800a6110  add     rsp, 88h
0x1800a6117  pop     r15
0x1800a6119  pop     r14
0x1800a611b  pop     rdi
0x1800a611c  pop     rsi
0x1800a611d  pop     rbx
0x1800a611e  pop     rbp
0x1800a611f  retn
```
