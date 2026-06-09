# CSpacePoolContext::~CSpacePoolContext(void)

- ea: `0x180013868`
- end: `0x180013918`
- name: `??1CSpacePoolContext@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(CSpacePoolContext *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180013610`
- `0x1800147d8`
- `0x180014ee8`

## callees

- `0x180006874`
- `0x1800136e0`
- `0x180013700`
- `0x180013868`

## import_xrefs

- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1800138c2`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1800138c2`

## pseudocode

```c
void __fastcall CSpacePoolContext::~CSpacePoolContext(CSpacePoolContext *this)
{
  PTP_CLEANUP_GROUP *v1; // rbx
  __int64 v3; // r9

  v1 = (PTP_CLEANUP_GROUP *)((char *)this + 72);
  v3 = *((_QWORD *)this + 9);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids, v3);
    }
    CloseThreadpoolCleanupGroupMembers(*v1, 0, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids, *v1);
    }
  }
  CHandleT<_TP_POOL *,ThreadPoolTrait>::~CHandleT<_TP_POOL *,ThreadPoolTrait>((struct _TP_POOL **)this + 11);
  CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>::~CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>(v1);
}

```

## disassembly

```asm
0x180013868  mov     [rsp+arg_0], rbx
0x18001386d  mov     [rsp+arg_8], rsi
0x180013872  push    rdi
0x180013873  sub     rsp, 20h
0x180013877  lea     rbx, [rcx+48h]
0x18001387b  mov     rdi, rcx
0x18001387e  mov     r9, [rbx]
0x180013881  test    r9, r9
0x180013884  jz      short loc_1800138F8
0x180013886  mov     rcx, cs:WPP_GLOBAL_Control
0x18001388d  lea     rsi, WPP_GLOBAL_Control
0x180013894  cmp     rcx, rsi
0x180013897  jz      short loc_1800138BA
0x180013899  test    byte ptr [rcx+1Ch], 1
0x18001389d  jz      short loc_1800138BA
0x18001389f  cmp     byte ptr [rcx+19h], 4
0x1800138a3  jb      short loc_1800138BA
0x1800138a5  mov     rcx, [rcx+10h]
0x1800138a9  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x1800138b0  mov     edx, 4Dh ; 'M'
0x1800138b5  call    WPP_SF_q
0x1800138ba  mov     rcx, [rbx]; ptpcg
0x1800138bd  xor     r8d, r8d; pvCleanupContext
0x1800138c0  xor     edx, edx; fCancelPendingCallbacks
0x1800138c2  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800138c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138cf  cmp     rcx, rsi
0x1800138d2  jz      short loc_1800138F8
0x1800138d4  test    byte ptr [rcx+1Ch], 1
0x1800138d8  jz      short loc_1800138F8
0x1800138da  cmp     byte ptr [rcx+19h], 4
0x1800138de  jb      short loc_1800138F8
0x1800138e0  mov     r9, [rbx]
0x1800138e3  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x1800138ea  mov     rcx, [rcx+10h]
0x1800138ee  mov     edx, 4Eh ; 'N'
0x1800138f3  call    WPP_SF_q
0x1800138f8  lea     rcx, [rdi+58h]
0x1800138fc  call    ??1?$CHandleT@PEAU_TP_POOL@@UThreadPoolTrait@@@@QEAA@XZ; CHandleT<_TP_POOL *,ThreadPoolTrait>::~CHandleT<_TP_POOL *,ThreadPoolTrait>(void)
0x180013901  mov     rcx, rbx
0x180013904  mov     rbx, [rsp+28h+arg_0]
0x180013909  mov     rsi, [rsp+28h+arg_8]
0x18001390e  add     rsp, 20h
0x180013912  pop     rdi
0x180013913  jmp     ??1?$CHandleT@PEAU_TP_CLEANUP_GROUP@@UThreadPoolCleanupGroupTrait@@@@QEAA@XZ; CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>::~CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>(void)
```
