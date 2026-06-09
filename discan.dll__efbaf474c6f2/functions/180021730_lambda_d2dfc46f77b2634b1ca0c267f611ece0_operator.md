# _lambda_d2dfc46f77b2634b1ca0c267f611ece0_::operator()

- ea: `0x180021730`
- end: `0x180021a0c`
- name: `_lambda_d2dfc46f77b2634b1ca0c267f611ece0_::operator()`
- size: `732`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180022450`

## callees

- `0x180001bc4`
- `0x180003134`
- `0x1800137d4`
- `0x180021730`
- `0x1800288ac`
- `0x18002c6f8`

## import_xrefs

- `ntdll!NtSetEvent` at `0x180021884`
- `ntdll!NtSetEvent` at `0x180021884`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180021757`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180021757`
- `KERNEL32!SubmitThreadpoolWork` at `0x1800219cc`
- `KERNEL32!SubmitThreadpoolWork` at `0x1800219cc`

## pseudocode

```c
void __fastcall lambda_d2dfc46f77b2634b1ca0c267f611ece0_::operator()(RTL_SRWLOCK **a1, __int64 **a2, PTP_WORK *a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 *v8; // rax
  RTL_SRWLOCK *v9; // rdx
  _QWORD *v10; // rcx
  PVOID Ptr; // r8
  unsigned __int64 v12; // r9
  unsigned __int64 v13; // r8
  PTP_WORK *v14; // r8
  unsigned __int64 v15; // r10
  RTL_SRWLOCK *v16; // r9
  unsigned __int64 v17; // r11
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  __int64 *v20; // rbx
  RTL_SRWLOCK *v21; // [rsp+50h] [rbp+8h] BYREF

  v21 = *a1 + 184;
  AcquireSRWLockExclusive(v21);
  v6 = (__int64)&(*a1)[182];
  v7 = *(_QWORD *)v6;
  if ( *(_QWORD *)(*(_QWORD *)v6 + 8LL) != v6 )
    __fastfail(3u);
  v8 = *a2;
  *v8 = v7;
  v8[1] = v6;
  *(_QWORD *)(v7 + 8) = v8;
  *(_QWORD *)v6 = v8;
  *a2 = 0;
  ++LODWORD((*a1)[185].Ptr);
  v9 = *a1;
  if ( LODWORD((*a1)[172].Ptr) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      Ptr = v9[178].Ptr;
      v12 = (unsigned __int64)a1[1]->Ptr;
      if ( (unsigned __int64)Ptr > v12
        || (v10 = WPP_GLOBAL_Control, v12 > (unsigned __int64)Ptr + 35024 * HIDWORD(v9[171].Ptr) - 35024) )
      {
        LODWORD(v13) = (v12 - (unsigned __int64)v9[177].Ptr) / 0x88D0 + 100;
      }
      else
      {
        v13 = (v12 - (unsigned __int64)v9[178].Ptr) / 0x88D0;
      }
      WPP_SF_DDZdd(
        v10[2],
        138,
        v13,
        *(_DWORD *)(*(_QWORD *)(*a1)->Ptr + 16LL),
        *(_DWORD *)(*(_QWORD *)(*a1)->Ptr + 36LL),
        *((_QWORD *)(*a1)->Ptr + 8),
        v13,
        (char)(*a1)[172].Ptr);
    }
    NtSetEvent((*a1)[148].Ptr, 0);
    CScrub::_ReleaseReservedIdlingThread(*a1, (struct _SCRUB_THREAD_CONTEXT *)a3, 1);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v14 = (PTP_WORK *)v9[178].Ptr;
      if ( v14 > a3 || a3 > &v14[4378 * HIDWORD(v9[171].Ptr) - 4378] )
        LOBYTE(v15) = (unsigned __int64)((char *)a3 - (char *)v9[177].Ptr) / 0x88D0 + 100;
      else
        v15 = (unsigned __int64)((char *)a3 - (char *)v9[178].Ptr) / 0x88D0;
      v16 = *a1;
      v17 = (unsigned __int64)(*a1)[178].Ptr;
      v18 = (unsigned __int64)a1[1]->Ptr;
      if ( v17 > v18 || v18 > v17 + 35024LL * (HIDWORD(v16[171].Ptr) - 1) )
        LOBYTE(v19) = (v18 - (unsigned __int64)v16[177].Ptr) / 0x88D0 + 100;
      else
        v19 = (v18 - (unsigned __int64)v16[178].Ptr) / 0x88D0;
      WPP_SF_DDZdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        139,
        -1287116741,
        *(_DWORD *)(*(_QWORD *)(*a1)->Ptr + 16LL),
        *(_DWORD *)(*(_QWORD *)(*a1)->Ptr + 36LL),
        *((_QWORD *)(*a1)->Ptr + 8),
        v19,
        v15);
    }
    SubmitThreadpoolWork(a3[2]);
  }
  CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v21);
  v20 = *a2;
  if ( *a2 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v20 + 5);
    operator delete(v20);
  }
  *a2 = 0;
}

```

## disassembly

```asm
0x180021730  mov     [rsp+arg_8], rbx
0x180021735  mov     [rsp+arg_10], rsi
0x18002173a  push    rdi
0x18002173b  sub     rsp, 40h
0x18002173f  mov     rbx, rcx
0x180021742  mov     rdi, r8
0x180021745  mov     rcx, [rcx]
0x180021748  mov     rsi, rdx
0x18002174b  add     rcx, 5C0h; SRWLock
0x180021752  mov     [rsp+48h+arg_0], rcx
0x180021757  call    cs:__imp_AcquireSRWLockExclusive
0x18002175d  mov     rcx, [rbx]
0x180021760  add     rcx, 5B0h
0x180021767  mov     r8, [rcx]
0x18002176a  cmp     [r8+8], rcx
0x18002176e  jz      short loc_180021777
0x180021770  mov     ecx, 3
0x180021775  int     29h; Win8: RtlFailFast(ecx)
0x180021777  mov     rax, [rsi]
0x18002177a  mov     [rax], r8
0x18002177d  mov     [rax+8], rcx
0x180021781  mov     [r8+8], rax
0x180021785  mov     [rcx], rax
0x180021788  mov     qword ptr [rsi], 0
0x18002178f  mov     rax, [rbx]
0x180021792  inc     dword ptr [rax+5C8h]
0x180021798  mov     rdx, [rbx]
0x18002179b  mov     r10d, [rdx+560h]
0x1800217a2  test    r10d, r10d
0x1800217a5  jz      loc_18002189D
0x1800217ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800217b2  lea     r8, WPP_GLOBAL_Control
0x1800217b9  cmp     rcx, r8
0x1800217bc  jz      loc_180021878
0x1800217c2  test    byte ptr [rcx+1Ch], 1
0x1800217c6  jz      loc_180021878
0x1800217cc  cmp     byte ptr [rcx+19h], 4
0x1800217d0  jb      loc_180021878
0x1800217d6  mov     rax, [rbx+8]
0x1800217da  mov     r8, [rdx+590h]
0x1800217e1  mov     r9, [rax]
0x1800217e4  cmp     r8, r9
0x1800217e7  ja      short loc_180021826
0x1800217e9  mov     eax, [rdx+55Ch]
0x1800217ef  dec     eax
0x1800217f1  cdqe
0x1800217f3  imul    rcx, rax, 88D0h
0x1800217fa  add     rcx, r8
0x1800217fd  cmp     r9, rcx
0x180021800  mov     rcx, cs:WPP_GLOBAL_Control
0x180021807  ja      short loc_180021826
0x180021809  sub     r9, [rdx+590h]
0x180021810  mov     rax, 77C150CFB348283Bh
0x18002181a  mul     r9
0x18002181d  mov     r8, rdx
0x180021820  shr     r8, 0Eh
0x180021824  jmp     short loc_180021842
0x180021826  sub     r9, [rdx+588h]
0x18002182d  mov     rax, 77C150CFB348283Bh
0x180021837  mul     r9
0x18002183a  shr     rdx, 0Eh
0x18002183e  lea     r8d, [rdx+64h]
0x180021842  mov     rax, [rbx]
0x180021845  mov     edx, 8Ah
0x18002184a  mov     rcx, [rcx+10h]
0x18002184e  mov     [rsp+48h+var_10], r10d
0x180021853  mov     [rsp+48h+var_18], r8d
0x180021858  mov     rax, [rax]
0x18002185b  mov     r9, [rax]
0x18002185e  mov     rax, [rax+40h]
0x180021862  mov     [rsp+48h+var_20], rax
0x180021867  mov     eax, [r9+24h]
0x18002186b  mov     r9d, [r9+10h]
0x18002186f  mov     [rsp+48h+var_28], eax
0x180021873  call    WPP_SF_DDZdd
0x180021878  mov     rcx, [rbx]
0x18002187b  xor     edx, edx; PreviousState
0x18002187d  mov     rcx, [rcx+4A0h]; EventHandle
0x180021884  call    cs:__imp_NtSetEvent
0x18002188a  mov     rcx, [rbx]; this
0x18002188d  mov     r8b, 1; unsigned __int8
0x180021890  mov     rdx, rdi; struct _SCRUB_THREAD_CONTEXT *
0x180021893  call    ?_ReleaseReservedIdlingThread@CScrub@@AEAAXPEAU_SCRUB_THREAD_CONTEXT@@E@Z; CScrub::_ReleaseReservedIdlingThread(_SCRUB_THREAD_CONTEXT *,uchar)
0x180021898  jmp     loc_1800219D2
0x18002189d  mov     rax, cs:WPP_GLOBAL_Control
0x1800218a4  lea     r8, WPP_GLOBAL_Control
0x1800218ab  cmp     rax, r8
0x1800218ae  jz      loc_1800219C8
0x1800218b4  test    byte ptr [rax+1Ch], 1
0x1800218b8  jz      loc_1800219C8
0x1800218be  cmp     byte ptr [rax+19h], 4
0x1800218c2  jb      loc_1800219C8
0x1800218c8  mov     r8, [rdx+590h]
0x1800218cf  cmp     r8, rdi
0x1800218d2  ja      short loc_180021910
0x1800218d4  mov     eax, [rdx+55Ch]
0x1800218da  dec     eax
0x1800218dc  cdqe
0x1800218de  imul    rcx, rax, 88D0h
0x1800218e5  add     rcx, r8
0x1800218e8  cmp     rdi, rcx
0x1800218eb  ja      short loc_180021910
0x1800218ed  mov     rcx, rdi
0x1800218f0  mov     r8, 77C150CFB348283Bh
0x1800218fa  sub     rcx, [rdx+590h]
0x180021901  mov     rax, r8
0x180021904  mul     rcx
0x180021907  mov     r10, rdx
0x18002190a  shr     r10, 0Eh
0x18002190e  jmp     short loc_180021932
0x180021910  mov     rcx, rdi
0x180021913  mov     r8, 77C150CFB348283Bh
0x18002191d  sub     rcx, [rdx+588h]
0x180021924  mov     rax, r8
0x180021927  mul     rcx
0x18002192a  shr     rdx, 0Eh
0x18002192e  lea     r10d, [rdx+64h]
0x180021932  mov     r9, [rbx]
0x180021935  mov     rax, [rbx+8]
0x180021939  mov     r11, [r9+590h]
0x180021940  mov     rdx, [rax]
0x180021943  cmp     r11, rdx
0x180021946  ja      short loc_180021978
0x180021948  mov     eax, [r9+55Ch]
0x18002194f  dec     eax
0x180021951  cdqe
0x180021953  imul    rcx, rax, 88D0h
0x18002195a  add     rcx, r11
0x18002195d  cmp     rdx, rcx
0x180021960  ja      short loc_180021978
0x180021962  sub     rdx, [r9+590h]
0x180021969  mov     rax, r8
0x18002196c  mul     rdx
0x18002196f  mov     rcx, rdx
0x180021972  shr     rcx, 0Eh
0x180021976  jmp     short loc_18002198C
0x180021978  sub     rdx, [r9+588h]
0x18002197f  mov     rax, r8
0x180021982  mul     rdx
0x180021985  shr     rdx, 0Eh
0x180021989  lea     ecx, [rdx+64h]
0x18002198c  mov     rax, [rbx]
0x18002198f  mov     edx, 8Bh
0x180021994  mov     [rsp+48h+var_10], r10d
0x180021999  mov     [rsp+48h+var_18], ecx
0x18002199d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219a4  mov     rax, [rax]
0x1800219a7  mov     rcx, [rcx+10h]
0x1800219ab  mov     r9, [rax]
0x1800219ae  mov     rax, [rax+40h]
0x1800219b2  mov     [rsp+48h+var_20], rax
0x1800219b7  mov     eax, [r9+24h]
0x1800219bb  mov     r9d, [r9+10h]
0x1800219bf  mov     [rsp+48h+var_28], eax
0x1800219c3  call    WPP_SF_DDZdd
0x1800219c8  mov     rcx, [rdi+10h]; pwk
0x1800219cc  call    cs:__imp_SubmitThreadpoolWork
0x1800219d2  lea     rcx, [rsp+48h+arg_0]; this
0x1800219d7  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x1800219dc  mov     rbx, [rsi]
0x1800219df  test    rbx, rbx
0x1800219e2  jz      short loc_1800219F5
0x1800219e4  lea     rcx, [rbx+28h]
0x1800219e8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800219ed  mov     rcx, rbx; Block
0x1800219f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800219f5  mov     rbx, [rsp+48h+arg_8]
0x1800219fa  mov     qword ptr [rsi], 0
0x180021a01  mov     rsi, [rsp+48h+arg_10]
0x180021a06  add     rsp, 40h
0x180021a0a  pop     rdi
0x180021a0b  retn
```
