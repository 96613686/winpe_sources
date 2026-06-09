# BthServClientRemoveSdpRecord(void *,unsigned __int64)

- ea: `0x180015edc`
- end: `0x18001619d`
- name: `?BthServClientRemoveSdpRecord@@YAKPEAX_K@Z`
- size: `705`
- prototype: `unsigned int __fastcall(void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180013c80`

## callees

- `0x18000dfcc`
- `0x180010128`
- `0x180011fd0`
- `0x1800120b8`
- `0x180012384`
- `0x180014050`
- `0x180015edc`
- `0x180017080`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015fec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001601f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015fec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001601f`

## pseudocode

```c
__int64 __fastcall BthServClientRemoveSdpRecord(_QWORD *a1, __int64 a2)
{
  __int64 v2; // rbx
  char v4; // di
  int v5; // r8d
  char *v7; // rdx
  char *v8; // rax
  char *v9; // rcx
  char *v10; // rbp
  char **v11; // rdx
  int v12; // edx
  int v13; // r8d
  DWORD v14; // esi
  volatile signed __int32 *v15; // rbx
  int v16; // edx
  int v17; // r8d
  int v18; // [rsp+20h] [rbp-78h]
  int v19; // [rsp+28h] [rbp-70h]
  HANDLE *v20; // [rsp+60h] [rbp-38h] BYREF
  volatile signed __int32 *v21; // [rsp+68h] [rbp-30h]
  DWORD NumberOfBytesTransferred; // [rsp+A0h] [rbp+8h] BYREF

  v2 = a2;
  NumberOfBytesTransferred = 0;
  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sqi(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v18,
      v19,
      23,
      (__int64)WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids);
  if ( !(unsigned int)BthServLockDbClients() )
    return 167;
  v7 = (char *)(a1 + 7);
  v8 = (char *)a1[7];
  if ( v8 == (char *)(a1 + 7) )
  {
LABEL_13:
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      v4 = 0;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = v4;
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_si(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v7,
        v5,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    ReleaseMutex(qword_1800470A0);
    return 160;
  }
  else
  {
    while ( 1 )
    {
      v9 = *(char **)v8;
      v10 = v8 - 8;
      if ( *((_QWORD *)v8 + 2) == v2 )
        break;
      v8 = *(char **)v8;
      if ( v9 == v7 )
        goto LABEL_13;
    }
    if ( *((char **)v9 + 1) != v8 || (v11 = (char **)*((_QWORD *)v8 + 1), *v11 != v8) )
      __fastfail(3u);
    *v11 = v9;
    *((_QWORD *)v9 + 1) = v11;
    ReleaseMutex(qword_1800470A0);
    BthServGlobals::GetSafeRadioHandle(&Globals, &v20);
    if ( v20 && (char *)*v20 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v14 = BthServOverlappedIoctl(*v20, 0x410218u, v10, 8u, 0, 0, &NumberOfBytesTransferred);
    else
      v14 = 6;
    if ( v21 )
    {
      if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
      {
        v15 = v21;
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
    if ( v14 )
    {
      LOBYTE(v12) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
    SdpFreePool(v10);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      v4 = 0;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = v4;
      LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v17, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    return v14;
  }
}

```

## disassembly

```asm
0x180015edc  mov     rax, rsp
0x180015edf  mov     [rax+10h], rbx
0x180015ee3  mov     [rax+18h], rbp
0x180015ee7  push    rsi
0x180015ee8  push    rdi
0x180015ee9  push    r12
0x180015eeb  push    r13
0x180015eed  push    r15
0x180015eef  sub     rsp, 70h
0x180015ef3  xor     ebp, ebp
0x180015ef5  mov     rbx, rdx
0x180015ef8  and     [rax+8], ebp
0x180015efb  mov     rsi, rcx
0x180015efe  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f05  lea     r12, WPP_GLOBAL_Control
0x180015f0c  mov     dil, 1
0x180015f0f  cmp     rcx, r12
0x180015f12  jz      short loc_180015F1F
0x180015f14  cmp     byte ptr [rcx+19h], 4
0x180015f18  jb      short loc_180015F1F
0x180015f1a  mov     dl, dil
0x180015f1d  jmp     short loc_180015F21
0x180015f1f  xor     dl, dl
0x180015f21  lea     r13, WPP_RECORDER_INITIALIZED
0x180015f28  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180015f2f  lea     r15, WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids
0x180015f36  setnz   r8b
0x180015f3a  test    dl, dl
0x180015f3c  jnz     short loc_180015F43
0x180015f3e  test    r8b, r8b
0x180015f41  jz      short loc_180015F66
0x180015f43  mov     r9, [rcx+28h]
0x180015f47  mov     rcx, [rcx+10h]
0x180015f4b  mov     [rsp+98h+var_48], rbx
0x180015f50  mov     [rsp+98h+var_50], rsi
0x180015f55  mov     [rsp+98h+var_60], r15
0x180015f5a  mov     word ptr [rsp+98h+lpNumberOfBytesTransferred], 17h
0x180015f61  call    WPP_RECORDER_AND_TRACE_SF_sqi
0x180015f66  call    ?BthServLockDbClients@@YAHXZ; BthServLockDbClients(void)
0x180015f6b  test    eax, eax
0x180015f6d  jnz     short loc_180015F79
0x180015f6f  mov     eax, 0A7h
0x180015f74  jmp     loc_180016183
0x180015f79  lea     rdx, [rsi+38h]
0x180015f7d  mov     rax, [rdx]
0x180015f80  cmp     rax, rdx
0x180015f83  jz      short loc_180015F9A
0x180015f85  mov     rcx, [rax]
0x180015f88  lea     rbp, [rax-8]
0x180015f8c  cmp     [rbp+18h], rbx
0x180015f90  jz      short loc_180016002
0x180015f92  mov     rax, rcx
0x180015f95  cmp     rcx, rdx
0x180015f98  jnz     short loc_180015F85
0x180015f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fa1  cmp     rcx, r12
0x180015fa4  jz      short loc_180015FAC
0x180015fa6  cmp     byte ptr [rcx+19h], 3
0x180015faa  jnb     short loc_180015FAF
0x180015fac  xor     dil, dil
0x180015faf  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180015fb6  setnz   r8b
0x180015fba  test    dil, dil
0x180015fbd  jnz     short loc_180015FC4
0x180015fbf  test    r8b, r8b
0x180015fc2  jz      short loc_180015FE5
0x180015fc4  mov     r9, [rcx+28h]
0x180015fc8  mov     dl, dil
0x180015fcb  mov     rcx, [rcx+10h]
0x180015fcf  mov     [rsp+98h+var_50], rbx
0x180015fd4  mov     [rsp+98h+var_60], r15
0x180015fd9  mov     word ptr [rsp+98h+lpNumberOfBytesTransferred], 18h
0x180015fe0  call    WPP_RECORDER_AND_TRACE_SF_si
0x180015fe5  mov     rcx, cs:qword_1800470A0; hMutex
0x180015fec  call    cs:__imp_ReleaseMutex
0x180015ff3  nop     dword ptr [rax+rax+00h]
0x180015ff8  mov     eax, 0A0h
0x180015ffd  jmp     loc_180016183
0x180016002  cmp     [rcx+8], rax
0x180016006  jnz     short loc_180016082
0x180016008  mov     rdx, [rax+8]
0x18001600c  cmp     [rdx], rax
0x18001600f  jnz     short loc_180016082
0x180016011  mov     [rdx], rcx
0x180016014  mov     [rcx+8], rdx
0x180016018  mov     rcx, cs:qword_1800470A0; hMutex
0x18001601f  call    cs:__imp_ReleaseMutex
0x180016026  nop     dword ptr [rax+rax+00h]
0x18001602b  lea     rdx, [rsp+98h+var_38]
0x180016030  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x180016037  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x18001603c  mov     rax, [rsp+98h+var_38]
0x180016041  test    rax, rax
0x180016044  jz      short loc_180016089
0x180016046  mov     rcx, [rax]; hFile
0x180016049  lea     rax, [rcx-1]
0x18001604d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016051  ja      short loc_180016089
0x180016053  lea     rax, [rsp+98h+NumberOfBytesTransferred]
0x18001605b  mov     r9d, 8; nInBufferSize
0x180016061  mov     [rsp+98h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180016066  mov     r8, rbp; lpInBuffer
0x180016069  and     [rsp+98h+var_70], 0
0x18001606e  mov     edx, 410218h; dwIoControlCode
0x180016073  and     [rsp+98h+var_78], 0
0x180016079  call    ?BthServOverlappedIoctl@@YAKPEAXK0K0KPEAK@Z; BthServOverlappedIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x18001607e  mov     esi, eax
0x180016080  jmp     short loc_18001608E
0x180016082  mov     ecx, 3
0x180016087  int     29h; Win8: RtlFailFast(ecx)
0x180016089  mov     esi, 6
0x18001608e  mov     rcx, [rsp+98h+var_30]
0x180016093  test    rcx, rcx
0x180016096  jz      short loc_1800160E1
0x180016098  or      r15d, 0FFFFFFFFh
0x18001609c  mov     eax, r15d
0x18001609f  lock xadd [rcx+8], eax
0x1800160a4  add     eax, r15d
0x1800160a7  jnz     short loc_1800160DA
0x1800160a9  mov     rbx, [rsp+98h+var_30]
0x1800160ae  mov     rcx, rbx
0x1800160b1  mov     rax, [rbx]
0x1800160b4  mov     rax, [rax]
0x1800160b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160bc  mov     eax, r15d
0x1800160bf  lock xadd [rbx+0Ch], eax
0x1800160c4  add     eax, r15d
0x1800160c7  jnz     short loc_1800160DA
0x1800160c9  mov     rcx, [rsp+98h+var_30]
0x1800160ce  mov     rax, [rcx]
0x1800160d1  mov     rax, [rax+8]
0x1800160d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160da  lea     r15, WPP_db4ee0e4eaba3bdc4454fe810b066fe8_Traceguids
0x1800160e1  test    esi, esi
0x1800160e3  jz      short loc_18001612F
0x1800160e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160ec  cmp     rcx, r12
0x1800160ef  jz      short loc_1800160FC
0x1800160f1  cmp     byte ptr [rcx+19h], 3
0x1800160f5  jb      short loc_1800160FC
0x1800160f7  mov     dl, dil
0x1800160fa  jmp     short loc_1800160FE
0x1800160fc  xor     dl, dl
0x1800160fe  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180016105  setnz   r8b
0x180016109  test    dl, dl
0x18001610b  jnz     short loc_180016112
0x18001610d  test    r8b, r8b
0x180016110  jz      short loc_18001612F
0x180016112  mov     r9, [rcx+28h]
0x180016116  mov     rcx, [rcx+10h]
0x18001611a  mov     dword ptr [rsp+98h+var_50], esi
0x18001611e  mov     [rsp+98h+var_60], r15
0x180016123  mov     word ptr [rsp+98h+lpNumberOfBytesTransferred], 19h
0x18001612a  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001612f  mov     rcx, rbp
0x180016132  call    SdpFreePool
0x180016137  mov     rcx, cs:WPP_GLOBAL_Control
0x18001613e  cmp     rcx, r12
0x180016141  jz      short loc_180016149
0x180016143  cmp     byte ptr [rcx+19h], 4
0x180016147  jnb     short loc_18001614C
0x180016149  xor     dil, dil
0x18001614c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180016153  setnz   r8b
0x180016157  test    dil, dil
0x18001615a  jnz     short loc_180016161
0x18001615c  test    r8b, r8b
0x18001615f  jz      short loc_180016181
0x180016161  mov     r9, [rcx+28h]
0x180016165  mov     dl, dil
0x180016168  mov     rcx, [rcx+10h]
0x18001616c  mov     dword ptr [rsp+98h+var_50], esi
0x180016170  mov     [rsp+98h+var_60], r15
0x180016175  mov     word ptr [rsp+98h+lpNumberOfBytesTransferred], 1Ah
0x18001617c  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180016181  mov     eax, esi
0x180016183  lea     r11, [rsp+98h+var_28]
0x180016188  mov     rbx, [r11+38h]
0x18001618c  mov     rbp, [r11+40h]
0x180016190  mov     rsp, r11
0x180016193  pop     r15
0x180016195  pop     r13
0x180016197  pop     r12
0x180016199  pop     rdi
0x18001619a  pop     rsi
0x18001619b  retn
```
