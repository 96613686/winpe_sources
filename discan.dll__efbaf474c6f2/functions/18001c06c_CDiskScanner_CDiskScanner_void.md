# CDiskScanner::~CDiskScanner(void)

- ea: `0x18001c06c`
- end: `0x18001c174`
- name: `??1CDiskScanner@@QEAA@XZ`
- size: `264`
- prototype: `void __fastcall(CDiskScanner *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800146c4`

## callees

- `0x180003180`
- `0x180013720`
- `0x18001c06c`
- `0x18001ebb0`
- `0x1800204b4`

## import_xrefs

- `msvcrt!free` at `0x18001c11b`
- `msvcrt!free` at `0x18001c133`
- `msvcrt!free` at `0x18001c14b`
- `msvcrt!free` at `0x18001c11b`
- `msvcrt!free` at `0x18001c133`
- `msvcrt!free` at `0x18001c14b`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18001c0c8`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18001c0c8`

## pseudocode

```c
void __fastcall CDiskScanner::~CDiskScanner(CDiskScanner *this, __int64 a2, __int64 a3)
{
  PTP_WORK *v3; // rdi
  __int64 v5; // rax
  __int64 v6; // r8

  v3 = (PTP_WORK *)((char *)this + 248);
  v5 = *((_QWORD *)this + 31);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, a3, *((unsigned int *)this + 4), v5);
    }
    WaitForThreadpoolWorkCallbacks(*v3, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v6, *((unsigned int *)this + 4), *v3);
    }
  }
  CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>(v3);
  CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>((char *)this + 232);
  free(*((void **)this + 28));
  *((_QWORD *)this + 28) = 0;
  free(*((void **)this + 26));
  *((_QWORD *)this + 26) = 0;
  free(*((void **)this + 24));
  *((_QWORD *)this + 24) = 0;
  ATL::CAtlList<ATL::CAutoPtr<CVolumeListEntry>,ATL::CAutoPtrElementTraits<CVolumeListEntry>>::RemoveAll((char *)this + 112);
}

```

## disassembly

```asm
0x18001c06c  mov     [rsp+arg_0], rbx
0x18001c071  mov     [rsp+arg_8], rbp
0x18001c076  push    rdi
0x18001c077  sub     rsp, 30h
0x18001c07b  lea     rdi, [rcx+0F8h]
0x18001c082  mov     rbx, rcx
0x18001c085  mov     rax, [rdi]
0x18001c088  test    rax, rax
0x18001c08b  jz      short loc_18001C100
0x18001c08d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c094  lea     rbp, WPP_GLOBAL_Control
0x18001c09b  cmp     rcx, rbp
0x18001c09e  jz      short loc_18001C0C3
0x18001c0a0  test    byte ptr [rcx+1Ch], 1
0x18001c0a4  jz      short loc_18001C0C3
0x18001c0a6  cmp     byte ptr [rcx+19h], 4
0x18001c0aa  jb      short loc_18001C0C3
0x18001c0ac  mov     r9d, [rbx+10h]
0x18001c0b0  mov     edx, 0Ch
0x18001c0b5  mov     rcx, [rcx+10h]
0x18001c0b9  mov     [rsp+38h+var_18], rax
0x18001c0be  call    WPP_SF_Dq
0x18001c0c3  mov     rcx, [rdi]; pwk
0x18001c0c6  xor     edx, edx; fCancelPendingCallbacks
0x18001c0c8  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001c0ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0d5  cmp     rcx, rbp
0x18001c0d8  jz      short loc_18001C100
0x18001c0da  test    byte ptr [rcx+1Ch], 1
0x18001c0de  jz      short loc_18001C100
0x18001c0e0  cmp     byte ptr [rcx+19h], 4
0x18001c0e4  jb      short loc_18001C100
0x18001c0e6  mov     rax, [rdi]
0x18001c0e9  mov     edx, 0Dh
0x18001c0ee  mov     r9d, [rbx+10h]
0x18001c0f2  mov     rcx, [rcx+10h]
0x18001c0f6  mov     [rsp+38h+var_18], rax
0x18001c0fb  call    WPP_SF_Dq
0x18001c100  mov     rcx, rdi; void *
0x18001c103  call    ??1?$CHandleT@PEAU_TP_WORK@@UThreadPoolWorkTrait@@@@QEAA@XZ; CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>(void)
0x18001c108  lea     rcx, [rbx+0E8h]
0x18001c10f  call    ??1?$CHandleT@PEAXUFileHandleTrait@@@@QEAA@XZ; CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>(void)
0x18001c114  mov     rcx, [rbx+0E0h]; Block
0x18001c11b  call    cs:__imp_free
0x18001c121  mov     qword ptr [rbx+0E0h], 0
0x18001c12c  mov     rcx, [rbx+0D0h]; Block
0x18001c133  call    cs:__imp_free
0x18001c139  mov     qword ptr [rbx+0D0h], 0
0x18001c144  mov     rcx, [rbx+0C0h]; Block
0x18001c14b  call    cs:__imp_free
0x18001c151  lea     rcx, [rbx+70h]
0x18001c155  mov     qword ptr [rbx+0C0h], 0
0x18001c160  mov     rbx, [rsp+38h+arg_0]
0x18001c165  mov     rbp, [rsp+38h+arg_8]
0x18001c16a  add     rsp, 30h
0x18001c16e  pop     rdi
0x18001c16f  jmp     ?RemoveAll@?$CAtlList@V?$CAutoPtr@VCVolumeListEntry@@@ATL@@V?$CAutoPtrElementTraits@VCVolumeListEntry@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoPtr<CVolumeListEntry>,ATL::CAutoPtrElementTraits<CVolumeListEntry>>::RemoveAll(void)
```
