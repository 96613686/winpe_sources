# CMessageTree::GetDataHere(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x180046070`
- end: `0x1800461c4`
- name: `?GetDataHere@CMessageTree@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CMessageTree *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180005748`
- `0x180021140`
- `0x180046070`
- `0x18004e328`

## import_xrefs

- `MSOERT2!HrGetStreamSize` at `0x18004613b`
- `MSOERT2!HrGetStreamSize` at `0x18004613b`
- `MSOERT2!HrCopyStreamToByte` at `0x180046182`
- `MSOERT2!HrCopyStreamToByte` at `0x180046182`
- `KERNEL32!GlobalUnlock` at `0x18004618e`
- `KERNEL32!GlobalUnlock` at `0x18004618e`
- `KERNEL32!GlobalSize` at `0x18004614f`
- `KERNEL32!GlobalSize` at `0x180046170`
- `KERNEL32!GlobalSize` at `0x18004614f`
- `KERNEL32!GlobalSize` at `0x180046170`
- `KERNEL32!GlobalLock` at `0x18004615e`
- `KERNEL32!GlobalLock` at `0x18004615e`
- `KERNEL32!LeaveCriticalSection` at `0x1800461a8`
- `KERNEL32!LeaveCriticalSection` at `0x1800461a8`
- `KERNEL32!EnterCriticalSection` at `0x1800460b2`
- `KERNEL32!EnterCriticalSection` at `0x1800460b2`

## pseudocode

```c
__int64 __fastcall CMessageTree::GetDataHere(CMessageTree *this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbp
  struct IStream *pstm; // r8
  int Source; // ebx
  CMessageTree *v9; // rcx
  struct IStream *v10; // rsi
  SIZE_T v11; // rbx
  LPVOID v12; // rbx
  SIZE_T v13; // rax
  unsigned int v15; // [rsp+48h] [rbp+10h] BYREF
  struct IStream *v16; // [rsp+58h] [rbp+20h] BYREF

  v16 = 0;
  v15 = 0;
  if ( a2 && a3 )
  {
    v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 368);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
    if ( (a2->tymed & 4) != 0 )
    {
      pstm = a3->pstm;
      if ( pstm )
      {
        a3->tymed = 4;
        Source = CMessageTree::_HrDataObjectGetSource((CMessageTree *)((char *)this - 40), a2->cfFormat, pstm);
        goto LABEL_17;
      }
    }
    else
    {
      if ( (a2->tymed & 1) == 0 )
      {
        Source = -2147221399;
        goto LABEL_17;
      }
      if ( a3->hBitmap )
      {
        a3->tymed = 1;
        if ( (int)MimeOleCreateVirtualStream(&v16) < 0 )
          goto LABEL_10;
        v9 = (CMessageTree *)((char *)this - 40);
        v10 = v16;
        Source = CMessageTree::_HrDataObjectGetSource(v9, a2->cfFormat, v16);
        if ( Source < 0 )
          goto LABEL_17;
        Source = HrGetStreamSize(v10, &v15);
        if ( Source < 0 )
          goto LABEL_17;
        v11 = v15;
        if ( v11 <= GlobalSize(a3->hBitmap) && (v12 = GlobalLock(a3->hBitmap)) != 0 )
        {
          v13 = GlobalSize(a3->hBitmap);
          Source = HrCopyStreamToByte(v10, v12, v13, 0);
          GlobalUnlock(a3->hBitmap);
        }
        else
        {
LABEL_10:
          Source = -2147286928;
        }
LABEL_17:
        OE_SafeReleaseAndNullPtr<IStream>(&v16);
        LeaveCriticalSection(v6);
        return (unsigned int)Source;
      }
    }
    Source = -2147024809;
    goto LABEL_17;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180046070  mov     [rsp+arg_0], rbx
0x180046075  push    rbp
0x180046076  push    rsi
0x180046077  push    rdi
0x180046078  sub     rsp, 20h
0x18004607c  mov     [rsp+38h+arg_18], 0
0x180046085  mov     rdi, r8
0x180046088  mov     [rsp+38h+arg_8], 0
0x180046090  mov     rbx, rdx
0x180046093  mov     rsi, rcx
0x180046096  test    rdx, rdx
0x180046099  jz      loc_1800461B2
0x18004609f  test    r8, r8
0x1800460a2  jz      loc_1800461B2
0x1800460a8  lea     rbp, [rcx+170h]
0x1800460af  mov     rcx, rbp; lpCriticalSection
0x1800460b2  call    cs:__imp_EnterCriticalSection
0x1800460b8  test    byte ptr [rbx+18h], 4
0x1800460bc  jz      short loc_1800460EA
0x1800460be  mov     r8, [rdi+8]; struct IStream *
0x1800460c2  test    r8, r8
0x1800460c5  jnz     short loc_1800460D1
0x1800460c7  mov     ebx, 80070057h
0x1800460cc  jmp     loc_18004619B
0x1800460d1  mov     dword ptr [rdi], 4
0x1800460d7  lea     rcx, [rsi-28h]; this
0x1800460db  movzx   edx, word ptr [rbx]; unsigned __int16
0x1800460de  call    ?_HrDataObjectGetSource@CMessageTree@@AEAAJGPEAUIStream@@@Z; CMessageTree::_HrDataObjectGetSource(ushort,IStream *)
0x1800460e3  mov     ebx, eax
0x1800460e5  jmp     loc_18004619B
0x1800460ea  test    byte ptr [rbx+18h], 1
0x1800460ee  jz      loc_180046196
0x1800460f4  cmp     qword ptr [rdi+8], 0
0x1800460f9  jz      short loc_1800460C7
0x1800460fb  lea     rcx, [rsp+38h+arg_18]
0x180046100  mov     dword ptr [rdi], 1
0x180046106  call    MimeOleCreateVirtualStream
0x18004610b  test    eax, eax
0x18004610d  jns     short loc_180046119
0x18004610f  mov     ebx, 80030070h
0x180046114  jmp     loc_18004619B
0x180046119  movzx   edx, word ptr [rbx]; unsigned __int16
0x18004611c  lea     rcx, [rsi-28h]; this
0x180046120  mov     rsi, [rsp+38h+arg_18]
0x180046125  mov     r8, rsi; struct IStream *
0x180046128  call    ?_HrDataObjectGetSource@CMessageTree@@AEAAJGPEAUIStream@@@Z; CMessageTree::_HrDataObjectGetSource(ushort,IStream *)
0x18004612d  mov     ebx, eax
0x18004612f  test    eax, eax
0x180046131  js      short loc_18004619B
0x180046133  lea     rdx, [rsp+38h+arg_8]
0x180046138  mov     rcx, rsi
0x18004613b  call    cs:__imp_HrGetStreamSize
0x180046141  mov     ebx, eax
0x180046143  test    eax, eax
0x180046145  js      short loc_18004619B
0x180046147  mov     rcx, [rdi+8]; hMem
0x18004614b  mov     ebx, [rsp+38h+arg_8]
0x18004614f  call    cs:__imp_GlobalSize
0x180046155  cmp     rbx, rax
0x180046158  ja      short loc_18004610F
0x18004615a  mov     rcx, [rdi+8]; hMem
0x18004615e  call    cs:__imp_GlobalLock
0x180046164  mov     rbx, rax
0x180046167  test    rax, rax
0x18004616a  jz      short loc_18004610F
0x18004616c  mov     rcx, [rdi+8]; hMem
0x180046170  call    cs:__imp_GlobalSize
0x180046176  xor     r9d, r9d
0x180046179  mov     rdx, rbx
0x18004617c  mov     r8, rax
0x18004617f  mov     rcx, rsi
0x180046182  call    cs:__imp_HrCopyStreamToByte
0x180046188  mov     rcx, [rdi+8]; hMem
0x18004618c  mov     ebx, eax
0x18004618e  call    cs:__imp_GlobalUnlock
0x180046194  jmp     short loc_18004619B
0x180046196  mov     ebx, 80040069h
0x18004619b  lea     rcx, [rsp+38h+arg_18]
0x1800461a0  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x1800461a5  mov     rcx, rbp; lpCriticalSection
0x1800461a8  call    cs:__imp_LeaveCriticalSection
0x1800461ae  mov     eax, ebx
0x1800461b0  jmp     short loc_1800461B7
0x1800461b2  mov     eax, 80070057h
0x1800461b7  mov     rbx, [rsp+38h+arg_0]
0x1800461bc  add     rsp, 20h
0x1800461c0  pop     rdi
0x1800461c1  pop     rsi
0x1800461c2  pop     rbp
0x1800461c3  retn
```
