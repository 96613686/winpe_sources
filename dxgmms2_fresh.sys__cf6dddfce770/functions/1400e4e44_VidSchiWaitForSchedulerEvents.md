# VidSchiWaitForSchedulerEvents

- ea: `0x1400e4e44`
- end: `0x1400e5277`
- name: `VidSchiWaitForSchedulerEvents`
- size: `1075`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f040`

## callees

- `0x1400049e0`
- `0x140010200`
- `0x14002a5e0`
- `0x14002bef0`
- `0x140058f50`
- `0x1400e4e44`
- `0x1400e5280`
- `0x1400e59e4`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1400e5115`
- `ntoskrnl!KeReadStateEvent` at `0x1400e5115`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400e4f82`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400e4f82`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400e5266`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400e5266`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400e5244`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400e5244`
- `ntoskrnl!KeResetEvent` at `0x1400e51c6`
- `ntoskrnl!KeResetEvent` at `0x1400e51c6`
- `dxgkrnl!g_TdrConfig` at `0x1400e50b4`
- `dxgkrnl!g_TdrConfig` at `0x1400e51f8`
- `HAL!KeQueryPerformanceCounter` at `0x1400e502d`
- `HAL!KeQueryPerformanceCounter` at `0x1400e502d`

## pseudocode

```c
__int64 __fastcall VidSchiWaitForSchedulerEvents(struct _VIDSCH_GLOBAL *a1)
{
  unsigned int v2; // edi
  unsigned int v3; // esi
  int v4; // eax
  char v5; // di
  char IsFlipQueueBusy; // r14
  union _LARGE_INTEGER *Timeout; // r9
  ULONG v8; // r10d
  ULONG v9; // r8d
  __int64 v10; // rax
  __int64 v11; // rdx
  PRKEVENT v12; // rcx
  unsigned int v13; // eax
  LARGE_INTEGER v15; // r9
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // rdx
  unsigned int v18; // r10d
  unsigned int i; // ecx
  __int64 *v20; // rax
  __int64 v21; // rax
  unsigned __int64 v22; // r9
  unsigned __int64 v23; // r8
  PRKEVENT v24; // r14
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v26; // [rsp+50h] [rbp-19h] BYREF
  PRKEVENT Event[4]; // [rsp+58h] [rbp-11h]
  PVOID Object[2]; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v29; // [rsp+88h] [rbp+1Fh]

  Event[1] = (PRKEVENT)((char *)a1 + 1544);
  Event[0] = (PRKEVENT)((char *)a1 + 1600);
  Event[2] = (PRKEVENT)((char *)a1 + 1712);
  while ( 1 )
  {
    v2 = 0;
    v3 = (unsigned __int8)VidSchiAcceptsIncomingWork(a1) + 1;
    while ( 1 )
    {
      if ( v2 >= v3 )
      {
        if ( v2 != v3 )
          goto LABEL_21;
        VidSchiProfilePerformanceTick(14, (_DWORD)a1, 0, 0, 0, 0, 0, 0);
        while ( 1 )
        {
          if ( (*((_DWORD *)a1 + 726) & 2) != 0 )
            ExReleaseResourceLite((PERESOURCE)((char *)a1 + 1232));
          do
          {
            v4 = *((_DWORD *)a1 + 218);
            v26 = 0;
            if ( v4 || *((_DWORD *)a1 + 19) || (v5 = 0, *((_DWORD *)a1 + 20)) )
              v5 = 1;
            IsFlipQueueBusy = VidSchiIsFlipQueueBusy(a1);
            if ( (unsigned __int8)VidSchiAcceptsIncomingWork(a1) )
            {
              PerformanceFrequency.QuadPart = 0;
              v15 = KeQueryPerformanceCounter(&PerformanceFrequency);
              if ( is_mul_ok(v15.QuadPart, 0x989680u) )
                v16 = (unsigned __int64)v15.QuadPart
                    * (unsigned __int128)0x989680uLL
                    / (unsigned __int64)PerformanceFrequency.QuadPart;
              else
                v16 = 10000000 * (v15.QuadPart / (unsigned __int64)PerformanceFrequency.QuadPart)
                    + 10000000
                    * (v15.QuadPart % (unsigned __int64)PerformanceFrequency.QuadPart)
                    / PerformanceFrequency.QuadPart;
              v17 = -1;
              if ( *((_BYTE *)a1 + 3480) )
                v17 = *((_QWORD *)a1 + 433);
              v18 = *((_DWORD *)a1 + 22);
              if ( v18 )
              {
                for ( i = 0; i < v18; ++i )
                {
                  if ( i >= *((_DWORD *)a1 + 212) )
                    v20 = (__int64 *)*((_QWORD *)a1 + 97);
                  else
                    v20 = (__int64 *)(*((_QWORD *)a1 + 97) + 8LL * i);
                  v21 = *v20;
                  v22 = *(_QWORD *)(v21 + 128);
                  if ( v22 && v17 >= v22 )
                    v17 = *(_QWORD *)(v21 + 128);
                }
              }
              if ( (v5 || IsFlipQueueBusy)
                && v17 >= v16 + ((10000000 * (unsigned __int64)(unsigned int)g_TdrConfig[1]) >> 1) )
              {
                v17 = v16 + ((10000000 * (unsigned __int64)(unsigned int)g_TdrConfig[1]) >> 1);
              }
              if ( v17 == -1 )
              {
                Timeout = 0;
                *((_BYTE *)a1 + 860) = 1;
                v8 = 3;
                goto LABEL_13;
              }
              if ( v17 <= v16 )
                v23 = 0;
              else
                v23 = v16 - v17;
              v26 = v23;
              Timeout = (union _LARGE_INTEGER *)&v26;
              v8 = 3;
            }
            else
            {
              Timeout = 0;
              v8 = 1;
            }
            *((_BYTE *)a1 + 860) = 0;
LABEL_13:
            *(_OWORD *)Object = 0;
            v9 = 0;
            v29 = 0;
            v10 = MEMORY[0xFFFFF78000000320];
            do
            {
              v11 = v9++;
              v12 = Event[v11];
              *(_QWORD *)&v12[1].Header.Lock = v10;
              Object[v11] = v12;
            }
            while ( v9 < v8 );
            v13 = KeWaitForMultipleObjects(v8, Object, WaitAny, Executive, 0, 0, Timeout, 0);
            *((_BYTE *)a1 + 860) = 0;
            v2 = v13;
          }
          while ( v13 > 1 && v13 != 258 );
          if ( (*((_DWORD *)a1 + 726) & 2) != 0 )
            ExAcquireResourceExclusiveLite((PERESOURCE)((char *)a1 + 1232), 1u);
          if ( v2 != 258 || !(unsigned int)VidSchiCheckHwProgress(a1) )
          {
            VidSchiProfilePerformanceTick(15, (_DWORD)a1, 0, 0, 0, 0, 0, 0);
            goto LABEL_21;
          }
        }
      }
      v24 = Event[v2];
      *(_QWORD *)&v24[2].Header.Lock = MEMORY[0xFFFFF78000000320];
      if ( KeReadStateEvent(v24) )
        break;
      ++v2;
    }
    v24[1].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)MEMORY[0xFFFFF78000000320];
    KeResetEvent(v24);
LABEL_21:
    if ( v2 )
      break;
    VidSchiHandleControlEvent(a1);
    if ( (unsigned __int8)VidSchIsTDRPending(a1) )
      return 258;
  }
  if ( (unsigned __int8)VidSchIsTDRPending(a1) )
    return 258;
  return v2;
}

```

## disassembly

```asm
0x1400e4e44  mov     [rsp-8+arg_8], rbx
0x1400e4e49  mov     [rsp-8+arg_10], rsi
0x1400e4e4e  push    rbp
0x1400e4e4f  push    rdi
0x1400e4e50  push    r13
0x1400e4e52  push    r14
0x1400e4e54  push    r15
0x1400e4e56  lea     rbp, [rsp-37h]
0x1400e4e5b  sub     rsp, 0A0h
0x1400e4e62  mov     rax, cs:__security_cookie
0x1400e4e69  xor     rax, rsp
0x1400e4e6c  mov     [rbp+57h+var_28], rax
0x1400e4e70  mov     rbx, rcx
0x1400e4e73  mov     r13d, 102h
0x1400e4e79  add     rcx, 608h
0x1400e4e80  mov     [rbp+57h+var_60], rcx
0x1400e4e84  xor     r15d, r15d
0x1400e4e87  lea     rax, [rcx+38h]
0x1400e4e8b  mov     [rbp+57h+Event], rax
0x1400e4e8f  lea     rax, [rbx+6B0h]
0x1400e4e96  mov     [rbp+57h+var_58], rax
0x1400e4e9a  mov     rcx, rbx
0x1400e4e9d  call    VidSchiAcceptsIncomingWork
0x1400e4ea2  movzx   esi, al
0x1400e4ea5  mov     edi, r15d
0x1400e4ea8  inc     esi
0x1400e4eaa  cmp     edi, esi
0x1400e4eac  jb      loc_1400E50FD
0x1400e4eb2  jnz     loc_1400E4FFD
0x1400e4eb8  mov     [rsp+0C0h+WaitBlockArray], r15
0x1400e4ebd  xor     r9d, r9d
0x1400e4ec0  mov     [rsp+0C0h+Timeout], r15
0x1400e4ec5  xor     r8d, r8d
0x1400e4ec8  mov     qword ptr [rsp+0C0h+Alertable], r15
0x1400e4ecd  mov     rdx, rbx
0x1400e4ed0  mov     qword ptr [rsp+0C0h+WaitMode], r15
0x1400e4ed5  lea     ecx, [r9+0Eh]
0x1400e4ed9  call    VidSchiProfilePerformanceTick
0x1400e4ede  mov     eax, [rbx+0B58h]
0x1400e4ee4  test    al, 2
0x1400e4ee6  jnz     loc_1400E523D
0x1400e4eec  mov     eax, [rbx+368h]
0x1400e4ef2  mov     [rbp+57h+var_70], r15
0x1400e4ef6  test    eax, eax
0x1400e4ef8  jz      loc_1400E5194
0x1400e4efe  mov     dil, 1
0x1400e4f01  mov     rcx, rbx
0x1400e4f04  call    VidSchiIsFlipQueueBusy
0x1400e4f09  mov     rcx, rbx
0x1400e4f0c  mov     r14b, al
0x1400e4f0f  call    VidSchiAcceptsIncomingWork
0x1400e4f14  test    al, al
0x1400e4f16  jnz     loc_1400E5025
0x1400e4f1c  mov     r9, r15
0x1400e4f1f  mov     r10d, 1
0x1400e4f25  mov     [rbx+35Ch], r15b
0x1400e4f2c  xorps   xmm0, xmm0
0x1400e4f2f  mov     rax, 0FFFFF78000000320h
0x1400e4f39  movups  xmmword ptr [rbp+57h+Object], xmm0
0x1400e4f3d  mov     r8d, r15d
0x1400e4f40  movups  [rbp+57h+var_38], xmm0
0x1400e4f44  mov     rax, [rax]
0x1400e4f47  mov     edx, r8d
0x1400e4f4a  inc     r8d
0x1400e4f4d  mov     rcx, [rbp+rdx*8+57h+Event]
0x1400e4f52  mov     [rcx+18h], rax
0x1400e4f56  mov     [rbp+rdx*8+57h+Object], rcx
0x1400e4f5b  cmp     r8d, r10d
0x1400e4f5e  jb      short loc_1400E4F47
0x1400e4f60  mov     [rsp+0C0h+WaitBlockArray], r15; WaitBlockArray
0x1400e4f65  lea     rdx, [rbp+57h+Object]; Object
0x1400e4f69  mov     [rsp+0C0h+Timeout], r9; Timeout
0x1400e4f6e  mov     ecx, r10d; Count
0x1400e4f71  xor     r9d, r9d; WaitReason
0x1400e4f74  mov     [rsp+0C0h+Alertable], r15b; Alertable
0x1400e4f79  mov     [rsp+0C0h+WaitMode], r15b; WaitMode
0x1400e4f7e  lea     r8d, [r9+1]; WaitType
0x1400e4f82  call    cs:__imp_KeWaitForMultipleObjects
0x1400e4f89  nop     dword ptr [rax+rax+00h]
0x1400e4f8e  mov     [rbx+35Ch], r15b
0x1400e4f95  mov     edi, eax
0x1400e4f97  cmp     eax, 1
0x1400e4f9a  ja      loc_1400E51EA
0x1400e4fa0  mov     ecx, [rbx+0B58h]
0x1400e4fa6  test    cl, 2
0x1400e4fa9  jnz     loc_1400E525D
0x1400e4faf  mov     [rbp+57h+var_80], r15b
0x1400e4fb3  cmp     edi, r13d
0x1400e4fb6  jnz     short loc_1400E4FD7
0x1400e4fb8  lea     rdx, [rbp+57h+var_80]
0x1400e4fbc  mov     rcx, rbx; struct _VIDSCH_GLOBAL *
0x1400e4fbf  call    VidSchiCheckHwProgress
0x1400e4fc4  test    eax, eax
0x1400e4fc6  jz      short loc_1400E4FD7
0x1400e4fc8  cmp     [rbp+57h+var_80], r15b
0x1400e4fcc  jz      loc_1400E4EDE
0x1400e4fd2  mov     edi, 1
0x1400e4fd7  mov     [rsp+0C0h+WaitBlockArray], r15
0x1400e4fdc  xor     r9d, r9d
0x1400e4fdf  mov     [rsp+0C0h+Timeout], r15
0x1400e4fe4  xor     r8d, r8d
0x1400e4fe7  mov     qword ptr [rsp+0C0h+Alertable], r15
0x1400e4fec  mov     rdx, rbx
0x1400e4fef  mov     qword ptr [rsp+0C0h+WaitMode], r15
0x1400e4ff4  lea     ecx, [r9+0Fh]
0x1400e4ff8  call    VidSchiProfilePerformanceTick
0x1400e4ffd  mov     rcx, rbx
0x1400e5000  test    edi, edi
0x1400e5002  jnz     loc_1400E515E
0x1400e5008  call    VidSchiHandleControlEvent
0x1400e500d  mov     rcx, rbx
0x1400e5010  call    VidSchIsTDRPending
0x1400e5015  test    al, al
0x1400e5017  jz      loc_1400E4E9A
0x1400e501d  mov     eax, r13d
0x1400e5020  jmp     loc_1400E516B
0x1400e5025  lea     rcx, [rbp+57h+PerformanceFrequency]; PerformanceFrequency
0x1400e5029  mov     qword ptr [rbp+57h+PerformanceFrequency], r15
0x1400e502d  call    cs:__imp_KeQueryPerformanceCounter
0x1400e5034  nop     dword ptr [rax+rax+00h]
0x1400e5039  mov     rcx, qword ptr [rbp+57h+PerformanceFrequency]
0x1400e503d  mov     r9, rax
0x1400e5040  mov     eax, 989680h
0x1400e5045  mul     r9
0x1400e5048  test    rdx, rdx
0x1400e504b  jnz     loc_1400E5130
0x1400e5051  div     rcx
0x1400e5054  mov     r8, rax
0x1400e5057  mov     al, [rbx+0D98h]
0x1400e505d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400e5061  test    al, al
0x1400e5063  jnz     loc_1400E51D7
0x1400e5069  mov     r10d, [rbx+58h]
0x1400e506d  test    r10d, r10d
0x1400e5070  jz      short loc_1400E50AA
0x1400e5072  mov     esi, [rbx+350h]
0x1400e5078  mov     ecx, r15d
0x1400e507b  mov     r11, [rbx+308h]
0x1400e5082  cmp     ecx, esi
0x1400e5084  jnb     loc_1400E5235
0x1400e508a  mov     eax, ecx
0x1400e508c  lea     rax, [r11+rax*8]
0x1400e5090  mov     rax, [rax]
0x1400e5093  mov     r9, [rax+80h]
0x1400e509a  test    r9, r9
0x1400e509d  jnz     loc_1400E5214
0x1400e50a3  inc     ecx
0x1400e50a5  cmp     ecx, r10d
0x1400e50a8  jb      short loc_1400E5082
0x1400e50aa  test    dil, dil
0x1400e50ad  jnz     short loc_1400E50B4
0x1400e50af  test    r14b, r14b
0x1400e50b2  jz      short loc_1400E50D4
0x1400e50b4  mov     rax, cs:?g_TdrConfig@@3U_TDR_CONFIG@@C; _TDR_CONFIG volatile g_TdrConfig
0x1400e50bb  mov     ecx, [rax+4]
0x1400e50be  imul    rcx, 989680h
0x1400e50c5  shr     rcx, 1
0x1400e50c8  add     rcx, r8
0x1400e50cb  cmp     rdx, rcx
0x1400e50ce  jnb     loc_1400E51F8
0x1400e50d4  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400e50d8  jz      loc_1400E5220
0x1400e50de  cmp     rdx, r8
0x1400e50e1  jbe     loc_1400E5255
0x1400e50e7  sub     r8, rdx
0x1400e50ea  mov     [rbp+57h+var_70], r8
0x1400e50ee  lea     r9, [rbp+57h+var_70]
0x1400e50f2  mov     r10d, 3
0x1400e50f8  jmp     loc_1400E4F25
0x1400e50fd  mov     eax, edi
0x1400e50ff  mov     r14, [rbp+rax*8+57h+Event]
0x1400e5104  mov     rax, ds:0FFFFF78000000320h
0x1400e510e  mov     rcx, r14; Event
0x1400e5111  mov     [r14+30h], rax
0x1400e5115  call    cs:__imp_KeReadStateEvent
0x1400e511c  nop     dword ptr [rax+rax+00h]
0x1400e5121  test    eax, eax
0x1400e5123  jnz     loc_1400E51B2
0x1400e5129  inc     edi
0x1400e512b  jmp     loc_1400E4EAA
0x1400e5130  xor     edx, edx
0x1400e5132  mov     rax, r9
0x1400e5135  div     rcx
0x1400e5138  imul    rax, rdx, 989680h
0x1400e513f  xor     edx, edx
0x1400e5141  div     rcx
0x1400e5144  xor     edx, edx
0x1400e5146  mov     r8, rax
0x1400e5149  mov     rax, r9
0x1400e514c  div     rcx
0x1400e514f  imul    rcx, rax, 989680h
0x1400e5156  add     r8, rcx
0x1400e5159  jmp     loc_1400E5057
0x1400e515e  call    VidSchIsTDRPending
0x1400e5163  test    al, al
0x1400e5165  cmovnz  edi, r13d
0x1400e5169  mov     eax, edi
0x1400e516b  mov     rcx, [rbp+57h+var_28]
0x1400e516f  xor     rcx, rsp; StackCookie
0x1400e5172  call    __security_check_cookie
0x1400e5177  lea     r11, [rsp+0C0h+var_20]
0x1400e517f  mov     rbx, [r11+38h]
0x1400e5183  mov     rsi, [r11+40h]
0x1400e5187  mov     rsp, r11
0x1400e518a  pop     r15
0x1400e518c  pop     r14
0x1400e518e  pop     r13
0x1400e5190  pop     rdi
0x1400e5191  pop     rbp
0x1400e5192  retn
0x1400e5194  mov     eax, [rbx+4Ch]
0x1400e5197  test    eax, eax
0x1400e5199  jnz     loc_1400E4EFE
0x1400e519f  mov     eax, [rbx+50h]
0x1400e51a2  mov     dil, r15b
0x1400e51a5  test    eax, eax
0x1400e51a7  jz      loc_1400E4F01
0x1400e51ad  jmp     loc_1400E4EFE
0x1400e51b2  mov     rax, 0FFFFF78000000320h
0x1400e51bc  mov     rcx, r14; Event
0x1400e51bf  mov     rax, [rax]
0x1400e51c2  mov     [r14+28h], rax
0x1400e51c6  call    cs:__imp_KeResetEvent
0x1400e51cd  nop     dword ptr [rax+rax+00h]
0x1400e51d2  jmp     loc_1400E4FFD
0x1400e51d7  mov     rax, [rbx+0D88h]
0x1400e51de  mov     rdx, [rbx+0D88h]
0x1400e51e5  jmp     loc_1400E5069
0x1400e51ea  cmp     edi, r13d
0x1400e51ed  jz      loc_1400E4FA0
0x1400e51f3  jmp     loc_1400E4EEC
0x1400e51f8  mov     rax, cs:?g_TdrConfig@@3U_TDR_CONFIG@@C; _TDR_CONFIG volatile g_TdrConfig
0x1400e51ff  mov     ecx, [rax+4]
0x1400e5202  imul    rdx, rcx, 989680h
0x1400e5209  shr     rdx, 1
0x1400e520c  add     rdx, r8
0x1400e520f  jmp     loc_1400E50D4
0x1400e5214  cmp     rdx, r9
0x1400e5217  cmovnb  rdx, r9
0x1400e521b  jmp     loc_1400E50A3
0x1400e5220  mov     r9, r15
0x1400e5223  mov     byte ptr [rbx+35Ch], 1
0x1400e522a  mov     r10d, 3
0x1400e5230  jmp     loc_1400E4F2C
0x1400e5235  mov     rax, r11
0x1400e5238  jmp     loc_1400E5090
0x1400e523d  lea     rcx, [rbx+4D0h]; Resource
0x1400e5244  call    cs:__imp_ExReleaseResourceLite
0x1400e524b  nop     dword ptr [rax+rax+00h]
0x1400e5250  jmp     loc_1400E4EEC
0x1400e5255  mov     r8, r15
0x1400e5258  jmp     loc_1400E50EA
0x1400e525d  lea     rcx, [rbx+4D0h]; Resource
0x1400e5264  mov     dl, 1; Wait
0x1400e5266  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400e526d  nop     dword ptr [rax+rax+00h]
0x1400e5272  jmp     loc_1400E4FAF
```
