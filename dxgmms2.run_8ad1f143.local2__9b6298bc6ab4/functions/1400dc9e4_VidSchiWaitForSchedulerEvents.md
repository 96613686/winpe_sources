# VidSchiWaitForSchedulerEvents

- ea: `0x1400dc9e4`
- end: `0x1400dce17`
- name: `VidSchiWaitForSchedulerEvents`
- size: `1075`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f5a0`

## callees

- `0x140004d60`
- `0x140010760`
- `0x14002d700`
- `0x14002ee30`
- `0x140058680`
- `0x1400dc9e4`
- `0x1400dce20`
- `0x1400dd584`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1400dccb5`
- `ntoskrnl!KeReadStateEvent` at `0x1400dccb5`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400dcb22`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400dcb22`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400dce06`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400dce06`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400dcde4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400dcde4`
- `ntoskrnl!KeResetEvent` at `0x1400dcd66`
- `ntoskrnl!KeResetEvent` at `0x1400dcd66`
- `dxgkrnl!g_TdrConfig` at `0x1400dcc54`
- `dxgkrnl!g_TdrConfig` at `0x1400dcd98`
- `HAL!KeQueryPerformanceCounter` at `0x1400dcbcd`
- `HAL!KeQueryPerformanceCounter` at `0x1400dcbcd`

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
              if ( (v5 || IsFlipQueueBusy) && v17 >= v16 + ((10000000 * (unsigned __int64)g_TdrConfig[1]) >> 1) )
                v17 = v16 + ((10000000 * (unsigned __int64)g_TdrConfig[1]) >> 1);
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
0x1400dc9e4  mov     [rsp-8+arg_8], rbx
0x1400dc9e9  mov     [rsp-8+arg_10], rsi
0x1400dc9ee  push    rbp
0x1400dc9ef  push    rdi
0x1400dc9f0  push    r13
0x1400dc9f2  push    r14
0x1400dc9f4  push    r15
0x1400dc9f6  lea     rbp, [rsp-37h]
0x1400dc9fb  sub     rsp, 0A0h
0x1400dca02  mov     rax, cs:__security_cookie
0x1400dca09  xor     rax, rsp
0x1400dca0c  mov     [rbp+57h+var_28], rax
0x1400dca10  mov     rbx, rcx
0x1400dca13  mov     r13d, 102h
0x1400dca19  add     rcx, 608h
0x1400dca20  mov     [rbp+57h+var_60], rcx
0x1400dca24  xor     r15d, r15d
0x1400dca27  lea     rax, [rcx+38h]
0x1400dca2b  mov     [rbp+57h+Event], rax
0x1400dca2f  lea     rax, [rbx+6B0h]
0x1400dca36  mov     [rbp+57h+var_58], rax
0x1400dca3a  mov     rcx, rbx
0x1400dca3d  call    VidSchiAcceptsIncomingWork
0x1400dca42  movzx   esi, al
0x1400dca45  mov     edi, r15d
0x1400dca48  inc     esi
0x1400dca4a  cmp     edi, esi
0x1400dca4c  jb      loc_1400DCC9D
0x1400dca52  jnz     loc_1400DCB9D
0x1400dca58  mov     [rsp+0C0h+WaitBlockArray], r15
0x1400dca5d  xor     r9d, r9d
0x1400dca60  mov     [rsp+0C0h+Timeout], r15
0x1400dca65  xor     r8d, r8d
0x1400dca68  mov     qword ptr [rsp+0C0h+Alertable], r15
0x1400dca6d  mov     rdx, rbx
0x1400dca70  mov     qword ptr [rsp+0C0h+WaitMode], r15
0x1400dca75  lea     ecx, [r9+0Eh]
0x1400dca79  call    VidSchiProfilePerformanceTick
0x1400dca7e  mov     eax, [rbx+0B58h]
0x1400dca84  test    al, 2
0x1400dca86  jnz     loc_1400DCDDD
0x1400dca8c  mov     eax, [rbx+368h]
0x1400dca92  mov     [rbp+57h+var_70], r15
0x1400dca96  test    eax, eax
0x1400dca98  jz      loc_1400DCD34
0x1400dca9e  mov     dil, 1
0x1400dcaa1  mov     rcx, rbx
0x1400dcaa4  call    VidSchiIsFlipQueueBusy
0x1400dcaa9  mov     rcx, rbx
0x1400dcaac  mov     r14b, al
0x1400dcaaf  call    VidSchiAcceptsIncomingWork
0x1400dcab4  test    al, al
0x1400dcab6  jnz     loc_1400DCBC5
0x1400dcabc  mov     r9, r15
0x1400dcabf  mov     r10d, 1
0x1400dcac5  mov     [rbx+35Ch], r15b
0x1400dcacc  xorps   xmm0, xmm0
0x1400dcacf  mov     rax, 0FFFFF78000000320h
0x1400dcad9  movups  xmmword ptr [rbp+57h+Object], xmm0
0x1400dcadd  mov     r8d, r15d
0x1400dcae0  movups  [rbp+57h+var_38], xmm0
0x1400dcae4  mov     rax, [rax]
0x1400dcae7  mov     edx, r8d
0x1400dcaea  inc     r8d
0x1400dcaed  mov     rcx, [rbp+rdx*8+57h+Event]
0x1400dcaf2  mov     [rcx+18h], rax
0x1400dcaf6  mov     [rbp+rdx*8+57h+Object], rcx
0x1400dcafb  cmp     r8d, r10d
0x1400dcafe  jb      short loc_1400DCAE7
0x1400dcb00  mov     [rsp+0C0h+WaitBlockArray], r15; WaitBlockArray
0x1400dcb05  lea     rdx, [rbp+57h+Object]; Object
0x1400dcb09  mov     [rsp+0C0h+Timeout], r9; Timeout
0x1400dcb0e  mov     ecx, r10d; Count
0x1400dcb11  xor     r9d, r9d; WaitReason
0x1400dcb14  mov     [rsp+0C0h+Alertable], r15b; Alertable
0x1400dcb19  mov     [rsp+0C0h+WaitMode], r15b; WaitMode
0x1400dcb1e  lea     r8d, [r9+1]; WaitType
0x1400dcb22  call    cs:__imp_KeWaitForMultipleObjects
0x1400dcb29  nop     dword ptr [rax+rax+00h]
0x1400dcb2e  mov     [rbx+35Ch], r15b
0x1400dcb35  mov     edi, eax
0x1400dcb37  cmp     eax, 1
0x1400dcb3a  ja      loc_1400DCD8A
0x1400dcb40  mov     ecx, [rbx+0B58h]
0x1400dcb46  test    cl, 2
0x1400dcb49  jnz     loc_1400DCDFD
0x1400dcb4f  mov     [rbp+57h+var_80], r15b
0x1400dcb53  cmp     edi, r13d
0x1400dcb56  jnz     short loc_1400DCB77
0x1400dcb58  lea     rdx, [rbp+57h+var_80]
0x1400dcb5c  mov     rcx, rbx; struct _VIDSCH_GLOBAL *
0x1400dcb5f  call    VidSchiCheckHwProgress
0x1400dcb64  test    eax, eax
0x1400dcb66  jz      short loc_1400DCB77
0x1400dcb68  cmp     [rbp+57h+var_80], r15b
0x1400dcb6c  jz      loc_1400DCA7E
0x1400dcb72  mov     edi, 1
0x1400dcb77  mov     [rsp+0C0h+WaitBlockArray], r15
0x1400dcb7c  xor     r9d, r9d
0x1400dcb7f  mov     [rsp+0C0h+Timeout], r15
0x1400dcb84  xor     r8d, r8d
0x1400dcb87  mov     qword ptr [rsp+0C0h+Alertable], r15
0x1400dcb8c  mov     rdx, rbx
0x1400dcb8f  mov     qword ptr [rsp+0C0h+WaitMode], r15
0x1400dcb94  lea     ecx, [r9+0Fh]
0x1400dcb98  call    VidSchiProfilePerformanceTick
0x1400dcb9d  mov     rcx, rbx
0x1400dcba0  test    edi, edi
0x1400dcba2  jnz     loc_1400DCCFE
0x1400dcba8  call    VidSchiHandleControlEvent
0x1400dcbad  mov     rcx, rbx
0x1400dcbb0  call    VidSchIsTDRPending
0x1400dcbb5  test    al, al
0x1400dcbb7  jz      loc_1400DCA3A
0x1400dcbbd  mov     eax, r13d
0x1400dcbc0  jmp     loc_1400DCD0B
0x1400dcbc5  lea     rcx, [rbp+57h+PerformanceFrequency]; PerformanceFrequency
0x1400dcbc9  mov     qword ptr [rbp+57h+PerformanceFrequency], r15
0x1400dcbcd  call    cs:__imp_KeQueryPerformanceCounter
0x1400dcbd4  nop     dword ptr [rax+rax+00h]
0x1400dcbd9  mov     rcx, qword ptr [rbp+57h+PerformanceFrequency]
0x1400dcbdd  mov     r9, rax
0x1400dcbe0  mov     eax, 989680h
0x1400dcbe5  mul     r9
0x1400dcbe8  test    rdx, rdx
0x1400dcbeb  jnz     loc_1400DCCD0
0x1400dcbf1  div     rcx
0x1400dcbf4  mov     r8, rax
0x1400dcbf7  mov     al, [rbx+0D98h]
0x1400dcbfd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400dcc01  test    al, al
0x1400dcc03  jnz     loc_1400DCD77
0x1400dcc09  mov     r10d, [rbx+58h]
0x1400dcc0d  test    r10d, r10d
0x1400dcc10  jz      short loc_1400DCC4A
0x1400dcc12  mov     esi, [rbx+350h]
0x1400dcc18  mov     ecx, r15d
0x1400dcc1b  mov     r11, [rbx+308h]
0x1400dcc22  cmp     ecx, esi
0x1400dcc24  jnb     loc_1400DCDD5
0x1400dcc2a  mov     eax, ecx
0x1400dcc2c  lea     rax, [r11+rax*8]
0x1400dcc30  mov     rax, [rax]
0x1400dcc33  mov     r9, [rax+80h]
0x1400dcc3a  test    r9, r9
0x1400dcc3d  jnz     loc_1400DCDB4
0x1400dcc43  inc     ecx
0x1400dcc45  cmp     ecx, r10d
0x1400dcc48  jb      short loc_1400DCC22
0x1400dcc4a  test    dil, dil
0x1400dcc4d  jnz     short loc_1400DCC54
0x1400dcc4f  test    r14b, r14b
0x1400dcc52  jz      short loc_1400DCC74
0x1400dcc54  mov     rax, cs:?g_TdrConfig@@3U_TDR_CONFIG@@C; _TDR_CONFIG volatile g_TdrConfig
0x1400dcc5b  mov     ecx, [rax+4]
0x1400dcc5e  imul    rcx, 989680h
0x1400dcc65  shr     rcx, 1
0x1400dcc68  add     rcx, r8
0x1400dcc6b  cmp     rdx, rcx
0x1400dcc6e  jnb     loc_1400DCD98
0x1400dcc74  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400dcc78  jz      loc_1400DCDC0
0x1400dcc7e  cmp     rdx, r8
0x1400dcc81  jbe     loc_1400DCDF5
0x1400dcc87  sub     r8, rdx
0x1400dcc8a  mov     [rbp+57h+var_70], r8
0x1400dcc8e  lea     r9, [rbp+57h+var_70]
0x1400dcc92  mov     r10d, 3
0x1400dcc98  jmp     loc_1400DCAC5
0x1400dcc9d  mov     eax, edi
0x1400dcc9f  mov     r14, [rbp+rax*8+57h+Event]
0x1400dcca4  mov     rax, ds:0FFFFF78000000320h
0x1400dccae  mov     rcx, r14; Event
0x1400dccb1  mov     [r14+30h], rax
0x1400dccb5  call    cs:__imp_KeReadStateEvent
0x1400dccbc  nop     dword ptr [rax+rax+00h]
0x1400dccc1  test    eax, eax
0x1400dccc3  jnz     loc_1400DCD52
0x1400dccc9  inc     edi
0x1400dcccb  jmp     loc_1400DCA4A
0x1400dccd0  xor     edx, edx
0x1400dccd2  mov     rax, r9
0x1400dccd5  div     rcx
0x1400dccd8  imul    rax, rdx, 989680h
0x1400dccdf  xor     edx, edx
0x1400dcce1  div     rcx
0x1400dcce4  xor     edx, edx
0x1400dcce6  mov     r8, rax
0x1400dcce9  mov     rax, r9
0x1400dccec  div     rcx
0x1400dccef  imul    rcx, rax, 989680h
0x1400dccf6  add     r8, rcx
0x1400dccf9  jmp     loc_1400DCBF7
0x1400dccfe  call    VidSchIsTDRPending
0x1400dcd03  test    al, al
0x1400dcd05  cmovnz  edi, r13d
0x1400dcd09  mov     eax, edi
0x1400dcd0b  mov     rcx, [rbp+57h+var_28]
0x1400dcd0f  xor     rcx, rsp; StackCookie
0x1400dcd12  call    __security_check_cookie
0x1400dcd17  lea     r11, [rsp+0C0h+var_20]
0x1400dcd1f  mov     rbx, [r11+38h]
0x1400dcd23  mov     rsi, [r11+40h]
0x1400dcd27  mov     rsp, r11
0x1400dcd2a  pop     r15
0x1400dcd2c  pop     r14
0x1400dcd2e  pop     r13
0x1400dcd30  pop     rdi
0x1400dcd31  pop     rbp
0x1400dcd32  retn
0x1400dcd34  mov     eax, [rbx+4Ch]
0x1400dcd37  test    eax, eax
0x1400dcd39  jnz     loc_1400DCA9E
0x1400dcd3f  mov     eax, [rbx+50h]
0x1400dcd42  mov     dil, r15b
0x1400dcd45  test    eax, eax
0x1400dcd47  jz      loc_1400DCAA1
0x1400dcd4d  jmp     loc_1400DCA9E
0x1400dcd52  mov     rax, 0FFFFF78000000320h
0x1400dcd5c  mov     rcx, r14; Event
0x1400dcd5f  mov     rax, [rax]
0x1400dcd62  mov     [r14+28h], rax
0x1400dcd66  call    cs:__imp_KeResetEvent
0x1400dcd6d  nop     dword ptr [rax+rax+00h]
0x1400dcd72  jmp     loc_1400DCB9D
0x1400dcd77  mov     rax, [rbx+0D88h]
0x1400dcd7e  mov     rdx, [rbx+0D88h]
0x1400dcd85  jmp     loc_1400DCC09
0x1400dcd8a  cmp     edi, r13d
0x1400dcd8d  jz      loc_1400DCB40
0x1400dcd93  jmp     loc_1400DCA8C
0x1400dcd98  mov     rax, cs:?g_TdrConfig@@3U_TDR_CONFIG@@C; _TDR_CONFIG volatile g_TdrConfig
0x1400dcd9f  mov     ecx, [rax+4]
0x1400dcda2  imul    rdx, rcx, 989680h
0x1400dcda9  shr     rdx, 1
0x1400dcdac  add     rdx, r8
0x1400dcdaf  jmp     loc_1400DCC74
0x1400dcdb4  cmp     rdx, r9
0x1400dcdb7  cmovnb  rdx, r9
0x1400dcdbb  jmp     loc_1400DCC43
0x1400dcdc0  mov     r9, r15
0x1400dcdc3  mov     byte ptr [rbx+35Ch], 1
0x1400dcdca  mov     r10d, 3
0x1400dcdd0  jmp     loc_1400DCACC
0x1400dcdd5  mov     rax, r11
0x1400dcdd8  jmp     loc_1400DCC30
0x1400dcddd  lea     rcx, [rbx+4D0h]; Resource
0x1400dcde4  call    cs:__imp_ExReleaseResourceLite
0x1400dcdeb  nop     dword ptr [rax+rax+00h]
0x1400dcdf0  jmp     loc_1400DCA8C
0x1400dcdf5  mov     r8, r15
0x1400dcdf8  jmp     loc_1400DCC8A
0x1400dcdfd  lea     rcx, [rbx+4D0h]; Resource
0x1400dce04  mov     dl, 1; Wait
0x1400dce06  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400dce0d  nop     dword ptr [rax+rax+00h]
0x1400dce12  jmp     loc_1400DCB4F
```
