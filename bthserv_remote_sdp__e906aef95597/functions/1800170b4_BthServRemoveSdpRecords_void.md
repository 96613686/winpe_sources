# BthServRemoveSdpRecords(void *)

- ea: `0x1800170b4`
- end: `0x1800173a7`
- name: `?BthServRemoveSdpRecords@@YAXPEAX@Z`
- size: `755`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180012f0c`

## callees

- `0x18000dfcc`
- `0x180010128`
- `0x180011fd0`
- `0x180012004`
- `0x1800120b8`
- `0x180012384`
- `0x180014050`
- `0x180017080`
- `0x1800170b4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017333`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017333`

## pseudocode

```c
void __fastcall BthServRemoveSdpRecords(char *a1)
{
  char v2; // di
  bool v3; // dl
  _QWORD *v4; // rcx
  bool v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 *v8; // rsi
  _QWORD **v9; // rbx
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  _QWORD *v12; // r14
  __int64 v13; // rcx
  volatile signed __int32 *v14; // rbx
  int v15; // [rsp+20h] [rbp-68h]
  int v16; // [rsp+28h] [rbp-60h]
  __int64 *v17; // [rsp+60h] [rbp-28h] BYREF
  volatile signed __int32 *v18; // [rsp+68h] [rbp-20h]
  DWORD NumberOfBytesTransferred; // [rsp+90h] [rbp+8h] BYREF

  NumberOfBytesTransferred = 0;
  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  if ( (unsigned int)BthServLockDbClients() )
  {
    BthServGlobals::GetSafeRadioHandle(&Globals, &v17);
    v8 = v17;
    if ( v17 && (unsigned __int64)(*v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v9 = (_QWORD **)(a1 + 56);
      while ( 1 )
      {
        v10 = *v9;
        if ( *v9 == v9 )
          break;
        if ( (_QWORD **)v10[1] != v9 || (v11 = (_QWORD *)*v10, *(_QWORD **)(*v10 + 8LL) != v10) )
          __fastfail(3u);
        *v9 = v11;
        v12 = v10 - 1;
        v11[1] = v9;
        LOBYTE(v6) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
        if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sqi(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v6,
            v7,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v15,
            v16,
            20,
            (__int64)WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids);
        }
        if ( v8 )
          v13 = *v8;
        else
          v13 = -1;
        BthServOverlappedIoctl((HANDLE)v13, 0x410218u, v12, 8u, 0, 0, &NumberOfBytesTransferred);
        SdpFreePool(v12);
      }
    }
    else
    {
      LOBYTE(v6) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        v14 = v18;
        (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64))v18)(v18, v6, v7);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    ReleaseMutex(qword_1800470A0);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      v2 = 0;
    v5 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_49;
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      v2 = 0;
    v5 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
LABEL_49:
      WPP_RECORDER_AND_TRACE_SF_s(v4[2], v2, v5, v4[5]);
  }
}

```

## disassembly

```asm
0x1800170b4  mov     rax, rsp
0x1800170b7  mov     [rax+10h], rbx
0x1800170bb  mov     [rax+18h], rbp
0x1800170bf  mov     [rax+20h], rsi
0x1800170c3  push    rdi
0x1800170c4  push    r13
0x1800170c6  push    r14
0x1800170c8  sub     rsp, 70h
0x1800170cc  and     dword ptr [rax+8], 0
0x1800170d0  mov     rbp, rcx
0x1800170d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170da  lea     r13, WPP_GLOBAL_Control
0x1800170e1  mov     dil, 1
0x1800170e4  cmp     rcx, r13
0x1800170e7  jz      short loc_1800170F4
0x1800170e9  cmp     byte ptr [rcx+19h], 4
0x1800170ed  jb      short loc_1800170F4
0x1800170ef  mov     dl, dil
0x1800170f2  jmp     short loc_1800170F6
0x1800170f4  xor     dl, dl
0x1800170f6  lea     r14, WPP_RECORDER_INITIALIZED
0x1800170fd  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180017104  lea     rbx, WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids
0x18001710b  setnz   r8b
0x18001710f  test    dl, dl
0x180017111  jnz     short loc_180017118
0x180017113  test    r8b, r8b
0x180017116  jz      short loc_180017136
0x180017118  mov     r9, [rcx+28h]
0x18001711c  mov     rcx, [rcx+10h]
0x180017120  mov     [rsp+88h+var_40], rbp
0x180017125  mov     [rsp+88h+var_50], rbx
0x18001712a  mov     word ptr [rsp+88h+lpNumberOfBytesTransferred], 12h
0x180017131  call    WPP_RECORDER_AND_TRACE_SF_si
0x180017136  call    ?BthServLockDbClients@@YAHXZ; BthServLockDbClients(void)
0x18001713b  test    eax, eax
0x18001713d  jnz     short loc_18001717E
0x18001713f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017146  cmp     rcx, r13
0x180017149  jz      short loc_180017151
0x18001714b  cmp     byte ptr [rcx+19h], 4
0x18001714f  jnb     short loc_180017154
0x180017151  xor     dil, dil
0x180017154  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18001715b  setnz   r8b
0x18001715f  test    dil, dil
0x180017162  jnz     short loc_18001716D
0x180017164  test    r8b, r8b
0x180017167  jz      loc_18001738C
0x18001716d  mov     [rsp+88h+var_50], rbx
0x180017172  mov     word ptr [rsp+88h+lpNumberOfBytesTransferred], 13h
0x180017179  jmp     loc_18001737C
0x18001717e  lea     rdx, [rsp+88h+var_28]
0x180017183  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x18001718a  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x18001718f  mov     rsi, [rsp+88h+var_28]
0x180017194  test    rsi, rsi
0x180017197  jz      loc_18001728D
0x18001719d  mov     rax, [rsi]
0x1800171a0  dec     rax
0x1800171a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800171a7  ja      loc_18001728D
0x1800171ad  lea     rbx, [rbp+38h]
0x1800171b1  mov     rax, [rbx]
0x1800171b4  cmp     rax, rbx
0x1800171b7  jz      loc_1800172DD
0x1800171bd  cmp     [rax+8], rbx
0x1800171c1  jnz     loc_180017286
0x1800171c7  mov     rcx, [rax]
0x1800171ca  cmp     [rcx+8], rax
0x1800171ce  jnz     loc_180017286
0x1800171d4  mov     [rbx], rcx
0x1800171d7  lea     r14, [rax-8]
0x1800171db  mov     [rcx+8], rbx
0x1800171df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171e6  cmp     rcx, r13
0x1800171e9  jz      short loc_1800171F6
0x1800171eb  cmp     byte ptr [rcx+19h], 4
0x1800171ef  jb      short loc_1800171F6
0x1800171f1  mov     dl, dil
0x1800171f4  jmp     short loc_1800171F8
0x1800171f6  xor     dl, dl
0x1800171f8  lea     rax, WPP_RECORDER_INITIALIZED
0x1800171ff  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180017206  setnz   r8b
0x18001720a  test    dl, dl
0x18001720c  jnz     short loc_180017213
0x18001720e  test    r8b, r8b
0x180017211  jz      short loc_180017240
0x180017213  mov     rax, [r14]
0x180017216  mov     r9, [rcx+28h]
0x18001721a  mov     rcx, [rcx+10h]
0x18001721e  mov     [rsp+88h+var_38], rbp
0x180017223  mov     [rsp+88h+var_40], rax
0x180017228  lea     rax, WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids
0x18001722f  mov     [rsp+88h+var_50], rax
0x180017234  mov     word ptr [rsp+88h+lpNumberOfBytesTransferred], 14h
0x18001723b  call    WPP_RECORDER_AND_TRACE_SF_sqi
0x180017240  test    rsi, rsi
0x180017243  jz      short loc_18001724A
0x180017245  mov     rcx, [rsi]
0x180017248  jmp     short loc_18001724E
0x18001724a  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001724e  lea     rax, [rsp+88h+NumberOfBytesTransferred]
0x180017256  mov     r9d, 8; nInBufferSize
0x18001725c  mov     [rsp+88h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180017261  mov     r8, r14; lpInBuffer
0x180017264  and     [rsp+88h+var_60], 0
0x180017269  mov     edx, 410218h; dwIoControlCode
0x18001726e  and     [rsp+88h+var_68], 0
0x180017274  call    ?BthServOverlappedIoctl@@YAKPEAXK0K0KPEAK@Z; BthServOverlappedIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x180017279  mov     rcx, r14
0x18001727c  call    SdpFreePool
0x180017281  jmp     loc_1800171B1
0x180017286  mov     ecx, 3
0x18001728b  int     29h; Win8: RtlFailFast(ecx)
0x18001728d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017294  cmp     rcx, r13
0x180017297  jz      short loc_1800172A4
0x180017299  cmp     byte ptr [rcx+19h], 3
0x18001729d  jb      short loc_1800172A4
0x18001729f  mov     dl, dil
0x1800172a2  jmp     short loc_1800172A6
0x1800172a4  xor     dl, dl
0x1800172a6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800172ad  setnz   r8b
0x1800172b1  test    dl, dl
0x1800172b3  jnz     short loc_1800172BA
0x1800172b5  test    r8b, r8b
0x1800172b8  jz      short loc_1800172E4
0x1800172ba  mov     r9, [rcx+28h]
0x1800172be  mov     rcx, [rcx+10h]
0x1800172c2  mov     dword ptr [rsp+88h+var_40], 80070006h
0x1800172ca  mov     [rsp+88h+var_50], rbx
0x1800172cf  mov     word ptr [rsp+88h+lpNumberOfBytesTransferred], 15h
0x1800172d6  call    WPP_RECORDER_AND_TRACE_SF_sD
0x1800172db  jmp     short loc_1800172E4
0x1800172dd  lea     r14, WPP_RECORDER_INITIALIZED
0x1800172e4  mov     rcx, [rsp+88h+var_20]
0x1800172e9  test    rcx, rcx
0x1800172ec  jz      short loc_18001732C
0x1800172ee  or      eax, 0FFFFFFFFh
0x1800172f1  lock xadd [rcx+8], eax
0x1800172f6  cmp     eax, 1
0x1800172f9  jnz     short loc_18001732C
0x1800172fb  mov     rbx, [rsp+88h+var_20]
0x180017300  mov     rcx, rbx
0x180017303  mov     rax, [rbx]
0x180017306  mov     rax, [rax]
0x180017309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001730e  or      eax, 0FFFFFFFFh
0x180017311  lock xadd [rbx+0Ch], eax
0x180017316  cmp     eax, 1
0x180017319  jnz     short loc_18001732C
0x18001731b  mov     rcx, [rsp+88h+var_20]
0x180017320  mov     rax, [rcx]
0x180017323  mov     rax, [rax+8]
0x180017327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001732c  mov     rcx, cs:qword_1800470A0; hMutex
0x180017333  call    cs:__imp_ReleaseMutex
0x18001733a  nop     dword ptr [rax+rax+00h]
0x18001733f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017346  cmp     rcx, r13
0x180017349  jz      short loc_180017351
0x18001734b  cmp     byte ptr [rcx+19h], 4
0x18001734f  jnb     short loc_180017354
0x180017351  xor     dil, dil
0x180017354  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18001735b  setnz   r8b
0x18001735f  test    dil, dil
0x180017362  jnz     short loc_180017369
0x180017364  test    r8b, r8b
0x180017367  jz      short loc_18001738C
0x180017369  lea     rdx, WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids
0x180017370  mov     [rsp+88h+var_50], rdx
0x180017375  mov     word ptr [rsp+88h+lpNumberOfBytesTransferred], 16h
0x18001737c  mov     r9, [rcx+28h]
0x180017380  mov     dl, dil
0x180017383  mov     rcx, [rcx+10h]
0x180017387  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001738c  lea     r11, [rsp+88h+var_18]
0x180017391  mov     rbx, [r11+28h]
0x180017395  mov     rbp, [r11+30h]
0x180017399  mov     rsi, [r11+38h]
0x18001739d  mov     rsp, r11
0x1800173a0  pop     r14
0x1800173a2  pop     r13
0x1800173a4  pop     rdi
0x1800173a5  retn
```
