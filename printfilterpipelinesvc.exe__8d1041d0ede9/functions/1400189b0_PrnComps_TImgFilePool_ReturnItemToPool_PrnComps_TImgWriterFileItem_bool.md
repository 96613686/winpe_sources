# PrnComps::TImgFilePool::ReturnItemToPool(PrnComps::TImgWriterFileItem *,bool)

- ea: `0x1400189b0`
- end: `0x140018ab9`
- name: `?ReturnItemToPool@TImgFilePool@PrnComps@@QEAAXPEAVTImgWriterFileItem@2@_N@Z`
- size: `265`
- prototype: `void __fastcall(PrnComps::TImgFilePool *this, struct PrnComps::TImgWriterFileItem *, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140019ac0`

## callees

- `0x14000537c`
- `0x1400172e8`
- `0x140017a4c`
- `0x140017c5c`
- `0x140017c94`
- `0x1400189b0`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140018a45`
- `KERNEL32!GetLastError` at `0x140018a45`
- `KERNEL32!LeaveCriticalSection` at `0x140018a7f`
- `KERNEL32!LeaveCriticalSection` at `0x140018a7f`
- `KERNEL32!SetFilePointer` at `0x140018a22`
- `KERNEL32!SetFilePointer` at `0x140018a22`
- `KERNEL32!SetEndOfFile` at `0x140018a3b`
- `KERNEL32!SetEndOfFile` at `0x140018a3b`

## pseudocode

```c
void __fastcall PrnComps::TImgFilePool::ReturnItemToPool(
        PrnComps::TImgFilePool *this,
        struct PrnComps::TImgWriterFileItem *a2,
        char a3)
{
  char *v5; // rbx
  void *v6; // rcx
  void *v7; // rcx
  DWORD LastError; // eax
  int v9; // edx
  _QWORD v11[2]; // [rsp+20h] [rbp-28h] BYREF
  int v12; // [rsp+30h] [rbp-18h]
  int v13; // [rsp+34h] [rbp-14h]

  v11[0] = this;
  v11[1] = PrnComps::TImgFilePool::RundownRelease;
  v13 = (unsigned __int64)PrnComps::TImgFilePool::RundownRelease >> 32;
  v12 = 0;
  if ( a3 )
  {
    v5 = (char *)this + 128;
    NCoreLibrary::TCriticalSection::Enter((PrnComps::TImgFilePool *)((char *)this + 128));
    if ( PrnComps::TImgFilePool::AddItemToTrimQueueInLock(this, a2) >= 0 )
    {
      v6 = (void *)*((_QWORD *)a2 + 4);
      if ( v6 == (void *)-1LL )
        v6 = 0;
      if ( SetFilePointer(v6, 0, 0, 0) != -1 )
      {
        v7 = (void *)*((_QWORD *)a2 + 4);
        if ( v7 == (void *)-1LL )
          v7 = 0;
        if ( SetEndOfFile(v7) )
          goto LABEL_10;
      }
      LastError = GetLastError();
      if ( (int)NCoreLibrary::HResultFromWin32((NCoreLibrary *)LastError, v9) < 0 )
        *((_BYTE *)this + 261) = 1;
      else
LABEL_10:
        NCoreLibrary::TList<PrnComps::TImgWriterFileItem::TEmbeddedLink>::AddAtTail((char *)this + 88, (char *)a2 + 104);
    }
    if ( (*((_DWORD *)v5 + 11))-- == 1 )
      *((_DWORD *)v5 + 10) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v5);
  }
  else if ( a2 )
  {
    (**(void (__fastcall ***)(struct PrnComps::TImgWriterFileItem *, __int64))a2)(a2, 1);
  }
  PrnExcept::TMethodRundown<PrnComps::TImgWriterFileItem>::~TMethodRundown<PrnComps::TImgWriterFileItem>(v11);
}

```

## disassembly

```asm
0x1400189b0  mov     r11, rsp
0x1400189b3  mov     [r11+8], rbx
0x1400189b7  mov     [r11+10h], rsi
0x1400189bb  push    rdi
0x1400189bc  sub     rsp, 40h
0x1400189c0  mov     [r11-28h], rcx
0x1400189c4  lea     rax, ?RundownRelease@TImgFilePool@PrnComps@@AEAAXXZ; PrnComps::TImgFilePool::RundownRelease(void)
0x1400189cb  mov     [r11-20h], rax
0x1400189cf  mov     rdi, rdx
0x1400189d2  mov     eax, [rsp+48h+var_1C]
0x1400189d6  mov     rsi, rcx
0x1400189d9  mov     [rsp+48h+var_14], eax
0x1400189dd  mov     [rsp+48h+var_18], 0
0x1400189e5  test    r8b, r8b
0x1400189e8  jz      loc_140018A87
0x1400189ee  lea     rbx, [rcx+80h]
0x1400189f5  mov     rcx, rbx; this
0x1400189f8  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x1400189fd  mov     rdx, rdi; struct PrnComps::TImgFileItemBase *
0x140018a00  mov     rcx, rsi; this
0x140018a03  call    ?AddItemToTrimQueueInLock@TImgFilePool@PrnComps@@QEAAJPEAVTImgFileItemBase@2@@Z; PrnComps::TImgFilePool::AddItemToTrimQueueInLock(PrnComps::TImgFileItemBase *)
0x140018a08  test    eax, eax
0x140018a0a  js      short loc_140018A6C
0x140018a0c  mov     rcx, [rdi+20h]
0x140018a10  xor     eax, eax
0x140018a12  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140018a16  cmovz   rcx, rax; hFile
0x140018a1a  xor     r9d, r9d; dwMoveMethod
0x140018a1d  xor     r8d, r8d; lpDistanceToMoveHigh
0x140018a20  xor     edx, edx; lDistanceToMove
0x140018a22  call    cs:__imp_SetFilePointer
0x140018a28  cmp     eax, 0FFFFFFFFh
0x140018a2b  jz      short loc_140018A45
0x140018a2d  mov     rcx, [rdi+20h]
0x140018a31  xor     eax, eax
0x140018a33  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140018a37  cmovz   rcx, rax; hFile
0x140018a3b  call    cs:__imp_SetEndOfFile
0x140018a41  test    eax, eax
0x140018a43  jnz     short loc_140018A56
0x140018a45  call    cs:__imp_GetLastError
0x140018a4b  mov     ecx, eax; this
0x140018a4d  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x140018a52  test    eax, eax
0x140018a54  js      short loc_140018A65
0x140018a56  lea     rdx, [rdi+68h]
0x140018a5a  lea     rcx, [rsi+58h]
0x140018a5e  call    ?AddAtTail@?$TList@VTEmbeddedLink@TImgWriterFileItem@PrnComps@@@NCoreLibrary@@QEAAJPEAVTLink@2@@Z; NCoreLibrary::TList<PrnComps::TImgWriterFileItem::TEmbeddedLink>::AddAtTail(NCoreLibrary::TLink *)
0x140018a63  jmp     short loc_140018A6C
0x140018a65  mov     byte ptr [rsi+105h], 1
0x140018a6c  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x140018a70  mov     eax, [rbx+2Ch]
0x140018a73  jnz     short loc_140018A7C
0x140018a75  mov     dword ptr [rbx+28h], 0
0x140018a7c  mov     rcx, rbx; lpCriticalSection
0x140018a7f  call    cs:__imp_LeaveCriticalSection
0x140018a85  jmp     short loc_140018A9F
0x140018a87  test    rdi, rdi
0x140018a8a  jz      short loc_140018A9F
0x140018a8c  mov     rax, [rdx]
0x140018a8f  mov     rcx, rdi
0x140018a92  mov     edx, 1
0x140018a97  mov     rax, [rax]
0x140018a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018a9f  lea     rcx, [rsp+48h+var_28]
0x140018aa4  call    ??1?$TMethodRundown@VTImgWriterFileItem@PrnComps@@@PrnExcept@@QEAA@XZ; PrnExcept::TMethodRundown<PrnComps::TImgWriterFileItem>::~TMethodRundown<PrnComps::TImgWriterFileItem>(void)
0x140018aa9  mov     rbx, [rsp+48h+arg_0]
0x140018aae  mov     rsi, [rsp+48h+arg_8]
0x140018ab3  add     rsp, 40h
0x140018ab7  pop     rdi
0x140018ab8  retn
```
