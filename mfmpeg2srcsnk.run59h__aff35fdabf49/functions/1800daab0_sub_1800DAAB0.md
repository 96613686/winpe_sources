# sub_1800DAAB0

- ea: `0x1800daab0`
- end: `0x1800dae22`
- name: `sub_1800DAAB0`
- size: `882`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180006960`
- `0x18000ac80`
- `0x18000c470`
- `0x18000d660`
- `0x18000e400`
- `0x1800251f0`
- `0x18002d790`
- `0x180037a98`
- `0x180098b50`
- `0x1800a9030`
- `0x1800daab0`
- `0x1800fcf10`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dab20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dabe3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dacc1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dad6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dab20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dabe3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dacc1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dad6a`
- `MFPlat!MFCreateMediaEvent` at `0x1800dabc1`
- `MFPlat!MFCreateMediaEvent` at `0x1800dabc1`

## string_xrefs

- `0x1800daad0`: `CMPEG2SampleMuxer::OnDrainSamplesComplete`

## pseudocode

```c
__int64 __fastcall sub_1800DAAB0(__int64 a1, unsigned int a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  int v6; // ebx
  __int64 v7; // r8
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  _BYTE v28[4]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v29; // [rsp+34h] [rbp-1Ch] BYREF
  IMFMediaEvent *ppEvent; // [rsp+38h] [rbp-18h] BYREF

  sub_180006960(v28, "CMPEG2SampleMuxer::OnDrainSamplesComplete", 995);
  v4 = *(_QWORD *)(a1 + 112);
  v29 = 0;
  ppEvent = 0;
  v6 = sub_18000D660(v4, a2, &v29);
  if ( v6 >= 0 )
  {
    v6 = MFCreateMediaEvent(0x25Bu, &Buf2, 0, 0, &ppEvent);
    if ( v6 >= 0 )
    {
      v6 = ((__int64 (__fastcall *)(IMFMediaEvent *, __int64 *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
             ppEvent,
             qword_18010F0C0,
             v29);
      if ( v6 >= 0 )
      {
        v6 = sub_1800251F0(*(_QWORD *)(a1 + 120), (__int64)ppEvent);
        if ( v6 < 0 )
        {
          v24 = (__int64 *)qword_18012EC10;
          if ( !qword_18012EC10 )
          {
            v25 = MFGetCallStackTracingWeakReference(0, v22);
            qword_18012EC10 = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (__int64 *)qword_18012EC10;
            }
            else
            {
              v24 = &qword_18012E0B0;
              qword_18012EC10 = (__int64)&qword_18012E0B0;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            v26 = sub_18000C470(v24, v22, v23);
            if ( *(_DWORD *)(v26 + 1996) != v6 )
              sub_18000E400(v26, "CMPEG2SampleMuxer::OnDrainSamplesComplete", 1010, (unsigned int)v6);
          }
          if ( (unsigned __int8)sub_1800A9030(v24, v22, v23) )
          {
            v11 = 119;
            goto LABEL_23;
          }
        }
      }
      else
      {
        v19 = (__int64 *)qword_18012EC10;
        if ( !qword_18012EC10 )
        {
          v20 = MFGetCallStackTracingWeakReference(0, v17);
          qword_18012EC10 = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
          {
            v19 = (__int64 *)qword_18012EC10;
          }
          else
          {
            v19 = &qword_18012E0B0;
            qword_18012EC10 = (__int64)&qword_18012E0B0;
          }
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          v21 = sub_18000C470(v19, v17, v18);
          if ( *(_DWORD *)(v21 + 1996) != v6 )
            sub_18000E400(v21, "CMPEG2SampleMuxer::OnDrainSamplesComplete", 1008, (unsigned int)v6);
        }
        if ( (unsigned __int8)sub_1800A9030(v19, v17, v18) )
        {
          v11 = 118;
          goto LABEL_23;
        }
      }
    }
    else
    {
      v14 = (__int64 *)qword_18012EC10;
      if ( !qword_18012EC10 )
      {
        v15 = MFGetCallStackTracingWeakReference(0, v12);
        qword_18012EC10 = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)qword_18012EC10;
        }
        else
        {
          v14 = &qword_18012E0B0;
          qword_18012EC10 = (__int64)&qword_18012E0B0;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = sub_18000C470(v14, v12, v13);
        if ( *(_DWORD *)(v16 + 1996) != v6 )
          sub_18000E400(v16, "CMPEG2SampleMuxer::OnDrainSamplesComplete", 1006, (unsigned int)v6);
      }
      if ( (unsigned __int8)sub_1800A9030(v14, v12, v13) )
      {
        v11 = 117;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v8 = (__int64 *)qword_18012EC10;
    if ( !qword_18012EC10 )
    {
      v9 = MFGetCallStackTracingWeakReference(0, v5);
      qword_18012EC10 = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)qword_18012EC10;
      }
      else
      {
        v8 = &qword_18012E0B0;
        qword_18012EC10 = (__int64)&qword_18012E0B0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = sub_18000C470(v8, v5, v7);
      if ( *(_DWORD *)(v10 + 1996) != v6 )
        sub_18000E400(v10, "CMPEG2SampleMuxer::OnDrainSamplesComplete", 1000, (unsigned int)v6);
    }
    if ( (unsigned __int8)sub_1800A9030(v8, v5, v7) )
    {
      v11 = 116;
LABEL_23:
      sub_180037A98(*((_QWORD *)RequestContext + 2), v11, &stru_1801158E0, a1, v6);
    }
  }
  sub_18002D790(&ppEvent);
  sub_18000AC80(v28);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800daab0  mov     [rsp-18h+arg_10], rbx
0x1800daab5  push    rbp
0x1800daab6  push    rdi
0x1800daab7  push    r14
0x1800daab9  mov     rbp, rsp
0x1800daabc  sub     rsp, 50h
0x1800daac0  mov     rax, cs:__security_cookie
0x1800daac7  xor     rax, rsp
0x1800daaca  mov     [rbp+var_10], rax
0x1800daace  mov     ebx, edx
0x1800daad0  lea     r14, aCmpeg2samplemu_1; "CMPEG2SampleMuxer::OnDrainSamplesComple"...
0x1800daad7  mov     rdi, rcx
0x1800daada  mov     rdx, r14
0x1800daadd  mov     r8d, 3E3h
0x1800daae3  lea     rcx, [rbp+var_20]
0x1800daae7  call    sub_180006960
0x1800daaec  mov     rcx, [rdi+70h]
0x1800daaf0  lea     r8, [rbp+var_1C]
0x1800daaf4  mov     edx, ebx
0x1800daaf6  mov     [rbp+var_1C], 0
0x1800daafd  mov     [rbp+var_18], 0
0x1800dab05  call    sub_18000D660
0x1800dab0a  mov     ebx, eax
0x1800dab0c  test    eax, eax
0x1800dab0e  jns     loc_1800DABA6
0x1800dab14  mov     rcx, cs:qword_18012EC10
0x1800dab1b  test    rcx, rcx
0x1800dab1e  jnz     short loc_1800DAB68
0x1800dab20  call    cs:MFGetCallStackTracingWeakReference
0x1800dab27  nop     dword ptr [rax+rax+00h]
0x1800dab2c  mov     cs:qword_18012EC10, rax
0x1800dab33  mov     rcx, rax
0x1800dab36  test    rax, rax
0x1800dab39  jz      short loc_1800DAB5A
0x1800dab3b  mov     rax, [rax]
0x1800dab3e  mov     edx, 7F0h
0x1800dab43  mov     rax, [rax+8]
0x1800dab47  call    cs:__guard_dispatch_icall_fptr
0x1800dab4d  test    eax, eax
0x1800dab4f  jz      short loc_1800DAB5A
0x1800dab51  mov     rcx, cs:qword_18012EC10
0x1800dab58  jmp     short loc_1800DAB68
0x1800dab5a  lea     rcx, qword_18012E0B0
0x1800dab61  mov     cs:qword_18012EC10, rcx
0x1800dab68  cmp     byte ptr [rcx+8], 0
0x1800dab6c  jz      short loc_1800DAB8F
0x1800dab6e  call    sub_18000C470
0x1800dab73  cmp     [rax+7CCh], ebx
0x1800dab79  jz      short loc_1800DAB8F
0x1800dab7b  mov     r9d, ebx
0x1800dab7e  mov     r8d, 3E8h
0x1800dab84  mov     rdx, r14
0x1800dab87  mov     rcx, rax
0x1800dab8a  call    sub_18000E400
0x1800dab8f  call    sub_1800A9030
0x1800dab94  cmp     al, 1
0x1800dab96  jb      loc_1800DAC7E
0x1800dab9c  mov     edx, 74h ; 't'
0x1800daba1  jmp     loc_1800DAC60
0x1800daba6  lea     rax, [rbp+var_18]
0x1800dabaa  xor     r9d, r9d; pvValue
0x1800dabad  xor     r8d, r8d; hrStatus
0x1800dabb0  mov     [rsp+50h+ppEvent], rax; ppEvent
0x1800dabb5  lea     rdx, Buf2; guidExtendedType
0x1800dabbc  mov     ecx, 25Bh; met
0x1800dabc1  call    cs:MFCreateMediaEvent
0x1800dabc8  nop     dword ptr [rax+rax+00h]
0x1800dabcd  mov     ebx, eax
0x1800dabcf  test    eax, eax
0x1800dabd1  jns     loc_1800DAC8C
0x1800dabd7  mov     rcx, cs:qword_18012EC10
0x1800dabde  test    rcx, rcx
0x1800dabe1  jnz     short loc_1800DAC2B
0x1800dabe3  call    cs:MFGetCallStackTracingWeakReference
0x1800dabea  nop     dword ptr [rax+rax+00h]
0x1800dabef  mov     cs:qword_18012EC10, rax
0x1800dabf6  mov     rcx, rax
0x1800dabf9  test    rax, rax
0x1800dabfc  jz      short loc_1800DAC1D
0x1800dabfe  mov     rax, [rax]
0x1800dac01  mov     edx, 7F0h
0x1800dac06  mov     rax, [rax+8]
0x1800dac0a  call    cs:__guard_dispatch_icall_fptr
0x1800dac10  test    eax, eax
0x1800dac12  jz      short loc_1800DAC1D
0x1800dac14  mov     rcx, cs:qword_18012EC10
0x1800dac1b  jmp     short loc_1800DAC2B
0x1800dac1d  lea     rcx, qword_18012E0B0
0x1800dac24  mov     cs:qword_18012EC10, rcx
0x1800dac2b  cmp     byte ptr [rcx+8], 0
0x1800dac2f  jz      short loc_1800DAC52
0x1800dac31  call    sub_18000C470
0x1800dac36  cmp     [rax+7CCh], ebx
0x1800dac3c  jz      short loc_1800DAC52
0x1800dac3e  mov     r9d, ebx
0x1800dac41  mov     r8d, 3EEh
0x1800dac47  mov     rdx, r14
0x1800dac4a  mov     rcx, rax
0x1800dac4d  call    sub_18000E400
0x1800dac52  call    sub_1800A9030
0x1800dac57  cmp     al, 1
0x1800dac59  jb      short loc_1800DAC7E
0x1800dac5b  mov     edx, 75h ; 'u'
0x1800dac60  mov     rcx, cs:RequestContext
0x1800dac67  lea     r8, stru_1801158E0
0x1800dac6e  mov     r9, rdi
0x1800dac71  mov     dword ptr [rsp+50h+ppEvent], ebx
0x1800dac75  mov     rcx, [rcx+10h]
0x1800dac79  call    sub_180037A98
0x1800dac7e  lea     rcx, [rbp+var_18]
0x1800dac82  call    sub_18002D790
0x1800dac87  jmp     loc_1800DADF9
0x1800dac8c  mov     rcx, [rbp+var_18]
0x1800dac90  lea     rdx, qword_18010F0C0
0x1800dac97  mov     r8d, [rbp+var_1C]
0x1800dac9b  mov     rax, [rcx]
0x1800dac9e  mov     rax, [rax+0A8h]
0x1800daca5  call    cs:__guard_dispatch_icall_fptr
0x1800dacab  mov     ebx, eax
0x1800dacad  test    eax, eax
0x1800dacaf  jns     loc_1800DAD47
0x1800dacb5  mov     rcx, cs:qword_18012EC10
0x1800dacbc  test    rcx, rcx
0x1800dacbf  jnz     short loc_1800DAD09
0x1800dacc1  call    cs:MFGetCallStackTracingWeakReference
0x1800dacc8  nop     dword ptr [rax+rax+00h]
0x1800daccd  mov     cs:qword_18012EC10, rax
0x1800dacd4  mov     rcx, rax
0x1800dacd7  test    rax, rax
0x1800dacda  jz      short loc_1800DACFB
0x1800dacdc  mov     rax, [rax]
0x1800dacdf  mov     edx, 7F0h
0x1800dace4  mov     rax, [rax+8]
0x1800dace8  call    cs:__guard_dispatch_icall_fptr
0x1800dacee  test    eax, eax
0x1800dacf0  jz      short loc_1800DACFB
0x1800dacf2  mov     rcx, cs:qword_18012EC10
0x1800dacf9  jmp     short loc_1800DAD09
0x1800dacfb  lea     rcx, qword_18012E0B0
0x1800dad02  mov     cs:qword_18012EC10, rcx
0x1800dad09  cmp     byte ptr [rcx+8], 0
0x1800dad0d  jz      short loc_1800DAD30
0x1800dad0f  call    sub_18000C470
0x1800dad14  cmp     [rax+7CCh], ebx
0x1800dad1a  jz      short loc_1800DAD30
0x1800dad1c  mov     r9d, ebx
0x1800dad1f  mov     r8d, 3F0h
0x1800dad25  mov     rdx, r14
0x1800dad28  mov     rcx, rax
0x1800dad2b  call    sub_18000E400
0x1800dad30  call    sub_1800A9030
0x1800dad35  cmp     al, 1
0x1800dad37  jb      loc_1800DAC7E
0x1800dad3d  mov     edx, 76h ; 'v'
0x1800dad42  jmp     loc_1800DAC60
0x1800dad47  mov     rdx, [rbp+var_18]
0x1800dad4b  mov     rcx, [rdi+78h]
0x1800dad4f  call    sub_1800251F0
0x1800dad54  mov     ebx, eax
0x1800dad56  test    eax, eax
0x1800dad58  jns     loc_1800DADF0
0x1800dad5e  mov     rcx, cs:qword_18012EC10
0x1800dad65  test    rcx, rcx
0x1800dad68  jnz     short loc_1800DADB2
0x1800dad6a  call    cs:MFGetCallStackTracingWeakReference
0x1800dad71  nop     dword ptr [rax+rax+00h]
0x1800dad76  mov     cs:qword_18012EC10, rax
0x1800dad7d  mov     rcx, rax
0x1800dad80  test    rax, rax
0x1800dad83  jz      short loc_1800DADA4
0x1800dad85  mov     rax, [rax]
0x1800dad88  mov     edx, 7F0h
0x1800dad8d  mov     rax, [rax+8]
0x1800dad91  call    cs:__guard_dispatch_icall_fptr
0x1800dad97  test    eax, eax
0x1800dad99  jz      short loc_1800DADA4
0x1800dad9b  mov     rcx, cs:qword_18012EC10
0x1800dada2  jmp     short loc_1800DADB2
0x1800dada4  lea     rcx, qword_18012E0B0
0x1800dadab  mov     cs:qword_18012EC10, rcx
0x1800dadb2  cmp     byte ptr [rcx+8], 0
0x1800dadb6  jz      short loc_1800DADD9
0x1800dadb8  call    sub_18000C470
0x1800dadbd  cmp     [rax+7CCh], ebx
0x1800dadc3  jz      short loc_1800DADD9
0x1800dadc5  mov     r9d, ebx
0x1800dadc8  mov     r8d, 3F2h
0x1800dadce  mov     rdx, r14
0x1800dadd1  mov     rcx, rax
0x1800dadd4  call    sub_18000E400
0x1800dadd9  call    sub_1800A9030
0x1800dadde  cmp     al, 1
0x1800dade0  jb      loc_1800DAC7E
0x1800dade6  mov     edx, 77h ; 'w'
0x1800dadeb  jmp     loc_1800DAC60
0x1800dadf0  lea     rcx, [rbp+var_18]
0x1800dadf4  call    sub_18002D790
0x1800dadf9  lea     rcx, [rbp+var_20]
0x1800dadfd  call    sub_18000AC80
0x1800dae02  mov     eax, ebx
0x1800dae04  mov     rcx, [rbp+var_10]
0x1800dae08  xor     rcx, rsp; StackCookie
0x1800dae0b  call    __security_check_cookie
0x1800dae10  mov     rbx, [rsp+50h+arg_10]
0x1800dae18  add     rsp, 50h
0x1800dae1c  pop     r14
0x1800dae1e  pop     rdi
0x1800dae1f  pop     rbp
0x1800dae20  retn
```
