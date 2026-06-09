# CDiskPnpMonitor::DeviceHandleNotifyCallback(HCMNOTIFICATION__ *,CDeviceNotifyData *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)

- ea: `0x180018f18`
- end: `0x1800191e5`
- name: `?DeviceHandleNotifyCallback@CDiskPnpMonitor@@AEAAXPEAUHCMNOTIFICATION__@@PEAVCDeviceNotifyData@@W4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z`
- size: `717`
- prototype: `void __fastcall(__int64, _QWORD *, _QWORD **, int, struct _CM_NOTIFY_EVENT_DATA *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019670`

## callees

- `0x1800064d8`
- `0x180009088`
- `0x1800137d4`
- `0x180018ef8`
- `0x180018f18`
- `0x1800196e0`
- `0x18001a014`
- `0x18001b1a0`
- `0x18001b408`
- `0x18001b4ac`
- `0x18001b5ac`
- `0x180020508`
- `0x180037620`
- `0x180039010`

## import_xrefs

- `KERNEL32!TrySubmitThreadpoolCallback` at `0x18001919b`
- `KERNEL32!TrySubmitThreadpoolCallback` at `0x18001919b`
- `KERNEL32!AcquireSRWLockShared` at `0x1800190a8`
- `KERNEL32!AcquireSRWLockShared` at `0x1800190a8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180019132`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180019132`

## pseudocode

```c
void __fastcall CDiskPnpMonitor::DeviceHandleNotifyCallback(
        __int64 a1,
        _QWORD *a2,
        _QWORD **a3,
        int a4,
        struct _CM_NOTIFY_EVENT_DATA *a5,
        unsigned int a6)
{
  unsigned int v10; // eax
  struct _STRING *CustomEventName; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r8
  unsigned int v15; // r9d
  int v16; // esi
  int v17; // esi
  void *v18; // rsi
  __int64 v19; // r8
  struct _STRING v20; // [rsp+40h] [rbp-78h] BYREF
  char v21[40]; // [rsp+50h] [rbp-68h] BYREF

  if ( a6 >= 0x20 )
  {
    v10 = *((_DWORD *)a5 + 7) + 32;
    if ( a6 >= v10 )
    {
      if ( a4 == 6 )
      {
        v20 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          CustomEventName = GetCustomEventName((const struct _GUID *)((char *)a5 + 8), &v20, v21, a6);
          WPP_SF_qLSaZ(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, (__int64)a3, 6, a3[9], CustomEventName);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qLS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, (_DWORD)a3, (_DWORD)a3, a4, (__int64)a3[9]);
      }
      if ( (int)CDiskPnpMonitor::WaitForInitializationCompletion((CDiskPnpMonitor *)a1) >= 0 )
      {
        *(_QWORD *)&v20.Length = a3 + 10;
        AcquireSRWLockShared((PSRWLOCK)a3 + 10);
        CAutoSrwSharedLock::~CAutoSrwSharedLock((CAutoSrwSharedLock *)&v20);
        if ( a2 == a3[11] )
        {
          v16 = a4 - 2;
          if ( v16 )
          {
            v17 = v16 - 1;
            if ( v17 )
            {
              if ( v17 == 3 )
                CDiskPnpMonitor::DiskCustomEventHandler((CDiskPnpMonitor *)*a3, (struct CDeviceNotifyData *)a3, a5, v15);
            }
            else
            {
              *(_QWORD *)&v20.Length = a3 + 10;
              AcquireSRWLockExclusive((PSRWLOCK)a3 + 10);
              CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((RTL_SRWLOCK **)&v20);
              v18 = (void *)CHandleT<void *,NtHandleTrait>::Detach((__int64 *)a3 + 11);
              CDiskPnpMonitor::NewDiskDeviceHandler((_QWORD **)a1, (__int64)a3, 2u);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v19, a3, v18);
              }
              TrySubmitThreadpoolCallback(CDiskPnpMonitor::UnregisterNotifyWork, v18, (PTP_CALLBACK_ENVIRON)(a1 + 32));
            }
          }
          else
          {
            (*(void (__fastcall **)(_QWORD, _QWORD *, _QWORD **))(*(_QWORD *)**a3 + 16LL))(**a3, a3[9], a3 + 2);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v14, a2, a3[11]);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids, a6, v10);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids, a6, 32);
  }
}

```

## disassembly

```asm
0x180018f18  mov     [rsp+arg_18], rbx
0x180018f1d  push    rbp
0x180018f1e  push    rsi
0x180018f1f  push    rdi
0x180018f20  push    r12
0x180018f22  push    r13
0x180018f24  push    r14
0x180018f26  push    r15
0x180018f28  sub     rsp, 80h
0x180018f2f  mov     rax, cs:__security_cookie
0x180018f36  xor     rax, rsp
0x180018f39  mov     [rsp+0B8h+var_40], rax
0x180018f3e  mov     r13, [rsp+0B8h+arg_20]
0x180018f46  mov     esi, r9d
0x180018f49  mov     r9d, dword ptr [rsp+0B8h+arg_28]; unsigned __int16
0x180018f51  mov     rbx, r8
0x180018f54  mov     r12, rdx
0x180018f57  mov     r14, rcx
0x180018f5a  cmp     r9d, 20h ; ' '
0x180018f5e  jnb     short loc_180018FAD
0x180018f60  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f67  lea     rdi, WPP_GLOBAL_Control
0x180018f6e  cmp     rcx, rdi
0x180018f71  jz      loc_1800191BD
0x180018f77  test    byte ptr [rcx+1Ch], 1
0x180018f7b  jz      loc_1800191BD
0x180018f81  cmp     byte ptr [rcx+19h], 2
0x180018f85  jb      loc_1800191BD
0x180018f8b  mov     edx, 1Eh
0x180018f90  mov     dword ptr [rsp+0B8h+var_98], 20h ; ' '
0x180018f98  mov     rcx, [rcx+10h]
0x180018f9c  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x180018fa3  call    WPP_SF_Dd
0x180018fa8  jmp     loc_1800191BD
0x180018fad  lea     rcx, [r13+8]; struct _GUID *
0x180018fb1  mov     eax, [rcx+14h]
0x180018fb4  add     eax, 20h ; ' '
0x180018fb7  cmp     r9d, eax
0x180018fba  jnb     short loc_180018FF2
0x180018fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fc3  lea     rdi, WPP_GLOBAL_Control
0x180018fca  cmp     rcx, rdi
0x180018fcd  jz      loc_1800191BD
0x180018fd3  test    byte ptr [rcx+1Ch], 1
0x180018fd7  jz      loc_1800191BD
0x180018fdd  cmp     byte ptr [rcx+19h], 2
0x180018fe1  jb      loc_1800191BD
0x180018fe7  mov     edx, 1Fh
0x180018fec  mov     dword ptr [rsp+0B8h+var_98], eax
0x180018ff0  jmp     short loc_180018F98
0x180018ff2  cmp     esi, 6
0x180018ff5  jnz     short loc_180019054
0x180018ff7  xorps   xmm0, xmm0
0x180018ffa  movups  xmmword ptr [rsp+0B8h+var_78.Length], xmm0
0x180018fff  mov     rax, cs:WPP_GLOBAL_Control
0x180019006  lea     rdi, WPP_GLOBAL_Control
0x18001900d  cmp     rax, rdi
0x180019010  jz      short loc_18001908C
0x180019012  test    byte ptr [rax+1Ch], 1
0x180019016  jz      short loc_18001908C
0x180019018  cmp     byte ptr [rax+19h], 4
0x18001901c  jb      short loc_18001908C
0x18001901e  lea     r8, [rsp+0B8h+var_68]; char *
0x180019023  lea     rdx, [rsp+0B8h+var_78]; struct _STRING *
0x180019028  call    ?GetCustomEventName@@YAPEAU_STRING@@PEBU_GUID@@PEAU1@PEADG@Z; GetCustomEventName(_GUID const *,_STRING *,char *,ushort)
0x18001902d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019034  mov     r9, rbx
0x180019037  mov     [rsp+0B8h+var_88], rax; __int64
0x18001903c  mov     rax, [rbx+48h]
0x180019040  mov     [rsp+0B8h+var_90], rax; __int64
0x180019045  mov     rcx, [rcx+10h]; LoggerHandle
0x180019049  mov     dword ptr [rsp+0B8h+var_98], esi; char
0x18001904d  call    WPP_SF_qLSaZ
0x180019052  jmp     short loc_18001908C
0x180019054  mov     rcx, cs:WPP_GLOBAL_Control
0x18001905b  lea     rdi, WPP_GLOBAL_Control
0x180019062  cmp     rcx, rdi
0x180019065  jz      short loc_18001908C
0x180019067  test    byte ptr [rcx+1Ch], 1
0x18001906b  jz      short loc_18001908C
0x18001906d  cmp     byte ptr [rcx+19h], 4
0x180019071  jb      short loc_18001908C
0x180019073  mov     rax, [r8+48h]
0x180019077  mov     r9, rbx
0x18001907a  mov     rcx, [rcx+10h]
0x18001907e  mov     [rsp+0B8h+var_90], rax
0x180019083  mov     dword ptr [rsp+0B8h+var_98], esi
0x180019087  call    WPP_SF_qLS
0x18001908c  mov     rcx, r14; this
0x18001908f  call    ?WaitForInitializationCompletion@CDiskPnpMonitor@@AEAAJXZ; CDiskPnpMonitor::WaitForInitializationCompletion(void)
0x180019094  test    eax, eax
0x180019096  js      loc_1800191BD
0x18001909c  lea     rbp, [rbx+50h]
0x1800190a0  mov     rcx, rbp; SRWLock
0x1800190a3  mov     qword ptr [rsp+0B8h+var_78.Length], rbp
0x1800190a8  call    cs:__imp_AcquireSRWLockShared
0x1800190ae  lea     rcx, [rsp+0B8h+var_78]; this
0x1800190b3  call    ??1CAutoSrwSharedLock@@QEAA@XZ; CAutoSrwSharedLock::~CAutoSrwSharedLock(void)
0x1800190b8  mov     rax, [rbx+58h]
0x1800190bc  cmp     r12, rax
0x1800190bf  jz      short loc_180019100
0x1800190c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190c8  cmp     rcx, rdi
0x1800190cb  jz      loc_1800191BD
0x1800190d1  test    byte ptr [rcx+1Ch], 1
0x1800190d5  jz      loc_1800191BD
0x1800190db  cmp     byte ptr [rcx+19h], 4
0x1800190df  jb      loc_1800191BD
0x1800190e5  mov     rcx, [rcx+10h]
0x1800190e9  mov     edx, 22h ; '"'
0x1800190ee  mov     r9, r12
0x1800190f1  mov     qword ptr [rsp+0B8h+var_98], rax
0x1800190f6  call    WPP_SF_qq
0x1800190fb  jmp     loc_1800191BD
0x180019100  sub     esi, 2
0x180019103  jz      loc_1800191A3
0x180019109  sub     esi, 1
0x18001910c  jz      short loc_18001912A
0x18001910e  cmp     esi, 3
0x180019111  jnz     loc_1800191BD
0x180019117  mov     rcx, [rbx]; this
0x18001911a  mov     r8, r13; struct _CM_NOTIFY_EVENT_DATA *
0x18001911d  mov     rdx, rbx; struct CDeviceNotifyData *
0x180019120  call    ?DiskCustomEventHandler@CDiskPnpMonitor@@AEAAXPEAVCDeviceNotifyData@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; CDiskPnpMonitor::DiskCustomEventHandler(CDeviceNotifyData *,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180019125  jmp     loc_1800191BD
0x18001912a  mov     rcx, rbp; SRWLock
0x18001912d  mov     qword ptr [rsp+0B8h+var_78.Length], rbp
0x180019132  call    cs:__imp_AcquireSRWLockExclusive
0x180019138  lea     rcx, [rsp+0B8h+var_78]; this
0x18001913d  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180019142  lea     rcx, [rbx+58h]
0x180019146  call    ?Detach@?$CHandleT@PEAXUNtHandleTrait@@@@QEAAPEAXXZ; CHandleT<void *,NtHandleTrait>::Detach(void)
0x18001914b  mov     rdx, rbx
0x18001914e  mov     r8d, 2
0x180019154  mov     rcx, r14
0x180019157  mov     rsi, rax
0x18001915a  call    ?NewDiskDeviceHandler@CDiskPnpMonitor@@AEAAJPEAVCDeviceNotifyData@@W4NewDiskDeviceHandlerType@1@@Z; CDiskPnpMonitor::NewDiskDeviceHandler(CDeviceNotifyData *,CDiskPnpMonitor::NewDiskDeviceHandlerType)
0x18001915f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019166  cmp     rcx, rdi
0x180019169  jz      short loc_18001918D
0x18001916b  test    byte ptr [rcx+1Ch], 1
0x18001916f  jz      short loc_18001918D
0x180019171  cmp     byte ptr [rcx+19h], 4
0x180019175  jb      short loc_18001918D
0x180019177  mov     rcx, [rcx+10h]
0x18001917b  mov     edx, 23h ; '#'
0x180019180  mov     r9, rbx
0x180019183  mov     qword ptr [rsp+0B8h+var_98], rsi
0x180019188  call    WPP_SF_qq
0x18001918d  lea     r8, [r14+20h]; pcbe
0x180019191  mov     rdx, rsi; pv
0x180019194  lea     rcx, ?UnregisterNotifyWork@CDiskPnpMonitor@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001919b  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800191a1  jmp     short loc_1800191BD
0x1800191a3  mov     rax, [rbx]
0x1800191a6  lea     r8, [rbx+10h]
0x1800191aa  mov     rdx, [rbx+48h]
0x1800191ae  mov     rcx, [rax]
0x1800191b1  mov     rax, [rcx]
0x1800191b4  mov     rax, [rax+10h]
0x1800191b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191bd  mov     rcx, [rsp+0B8h+var_40]
0x1800191c2  xor     rcx, rsp; StackCookie
0x1800191c5  call    __security_check_cookie
0x1800191ca  mov     rbx, [rsp+0B8h+arg_18]
0x1800191d2  add     rsp, 80h
0x1800191d9  pop     r15
0x1800191db  pop     r14
0x1800191dd  pop     r13
0x1800191df  pop     r12
0x1800191e1  pop     rdi
0x1800191e2  pop     rsi
0x1800191e3  pop     rbp
0x1800191e4  retn
```
