# Active(IKsPin *,ulong,void *,KSPIN_COMMUNICATION,IPin *,CGenericList<CAggregateMarshaler> *,CKsProxy *)

- ea: `0x18000eff4`
- end: `0x18000f13d`
- name: `?Active@@YAJPEAUIKsPin@@KPEAXW4KSPIN_COMMUNICATION@@PEAUIPin@@PEAV?$CGenericList@VCAggregateMarshaler@@@@PEAVCKsProxy@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(struct IKsPin *, unsigned int, HANDLE hFile, enum KSSTATE, int, __int64 *, CKsProxy *)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001c110`
- `0x180026760`
- `0x18002cf80`

## callees

- `0x18000a72c`
- `0x18000d7bc`
- `0x18000eff4`
- `0x18000f2a8`
- `0x1800172b4`
- `0x180018060`
- `0x18002ca70`
- `0x1800377a8`
- `0x18003b750`

## pseudocode

```c
__int64 __fastcall Active(
        struct IKsPin *a1,
        unsigned int a2,
        HANDLE hFile,
        enum KSSTATE a4,
        int a5,
        __int64 *a6,
        CKsProxy *a7)
{
  PVOID *v10; // rcx
  int State; // ebx
  enum KSSTATE v12; // eax
  enum KSSTATE OutBuffer; // [rsp+68h] [rbp+20h] BYREF

  OutBuffer = a4;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, a1);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hFile )
  {
    OutBuffer = KSSTATE_STOP;
    State = GetState(hFile, &OutBuffer);
    v12 = OutBuffer;
    if ( State < 0 && (State != -2147023792 || OutBuffer != KSSTATE_PAUSE) )
      return (unsigned int)State;
    if ( OutBuffer == KSSTATE_STOP )
    {
      State = CKsProxy::PropagateAcquire(a7, a1, 1u);
      FixupPipe(a1, a2);
      if ( State < 0 )
        return (unsigned int)State;
      v12 = OutBuffer;
    }
    if ( v12 == KSSTATE_PAUSE || (State = SetState((char *)hFile, KSSTATE_PAUSE), State >= 0) )
    {
      DistributePause(a6);
    }
    else if ( OutBuffer == KSSTATE_STOP )
    {
      SetState((char *)hFile, KSSTATE_STOP);
      DistributeStop(a6);
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    State = 0;
  }
  if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 25) >= 2u )
    WPP_SF_qqD(v10[2], 15, hFile, a1);
  return (unsigned int)State;
}

```

## disassembly

```asm
0x18000eff4  mov     rax, rsp
0x18000eff7  mov     [rax+8], rbx
0x18000effb  mov     [rax+10h], rbp
0x18000efff  mov     [rax+20h], r9d
0x18000f003  push    rsi
0x18000f004  push    rdi
0x18000f005  push    r15
0x18000f007  sub     rsp, 30h
0x18000f00b  mov     rdi, r8
0x18000f00e  mov     ebp, edx
0x18000f010  mov     rsi, rcx
0x18000f013  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f01a  lea     r15, WPP_GLOBAL_Control
0x18000f021  cmp     rcx, r15
0x18000f024  jz      short loc_18000F04F
0x18000f026  cmp     byte ptr [rcx+19h], 2
0x18000f02a  jb      short loc_18000F04F
0x18000f02c  mov     rcx, [rcx+10h]
0x18000f030  mov     edx, 0Eh
0x18000f035  mov     [rax-28h], r8
0x18000f039  mov     r9, rsi
0x18000f03c  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x18000f043  call    WPP_SF_qq
0x18000f048  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f04f  test    rdi, rdi
0x18000f052  jz      loc_18000F100
0x18000f058  lea     rdx, [rsp+48h+OutBuffer]; lpOutBuffer
0x18000f05d  mov     [rsp+48h+OutBuffer], 0
0x18000f065  mov     rcx, rdi; hFile
0x18000f068  call    ?GetState@@YAJPEAXPEAW4KSSTATE@@@Z; GetState(void *,KSSTATE *)
0x18000f06d  mov     ebx, eax
0x18000f06f  mov     eax, [rsp+48h+OutBuffer]
0x18000f073  test    ebx, ebx
0x18000f075  jns     short loc_18000F08C
0x18000f077  cmp     ebx, 80070450h
0x18000f07d  jnz     loc_18000F127
0x18000f083  cmp     eax, 2
0x18000f086  jnz     loc_18000F127
0x18000f08c  test    eax, eax
0x18000f08e  jnz     short loc_18000F0B8
0x18000f090  mov     rcx, [rsp+48h+arg_30]; this
0x18000f098  lea     r8d, [rax+1]; unsigned int
0x18000f09c  mov     rdx, rsi; struct IKsPin *
0x18000f09f  call    ?PropagateAcquire@CKsProxy@@QEAAJPEAUIKsPin@@K@Z; CKsProxy::PropagateAcquire(IKsPin *,ulong)
0x18000f0a4  mov     edx, ebp; unsigned int
0x18000f0a6  mov     rcx, rsi; struct IKsPin *
0x18000f0a9  mov     ebx, eax
0x18000f0ab  call    ?FixupPipe@@YAJPEAUIKsPin@@K@Z; FixupPipe(IKsPin *,ulong)
0x18000f0b0  test    ebx, ebx
0x18000f0b2  js      short loc_18000F127
0x18000f0b4  mov     eax, [rsp+48h+OutBuffer]
0x18000f0b8  cmp     eax, 2
0x18000f0bb  jz      short loc_18000F0ED
0x18000f0bd  mov     edx, 2; enum KSSTATE
0x18000f0c2  mov     rcx, rdi; void *
0x18000f0c5  call    ?SetState@@YAJPEAXW4KSSTATE@@@Z; SetState(void *,KSSTATE)
0x18000f0ca  mov     ebx, eax
0x18000f0cc  test    eax, eax
0x18000f0ce  jns     short loc_18000F0ED
0x18000f0d0  cmp     [rsp+48h+OutBuffer], 0
0x18000f0d5  jnz     short loc_18000F0F7
0x18000f0d7  xor     edx, edx; enum KSSTATE
0x18000f0d9  mov     rcx, rdi; void *
0x18000f0dc  call    ?SetState@@YAJPEAXW4KSSTATE@@@Z; SetState(void *,KSSTATE)
0x18000f0e1  mov     rcx, [rsp+48h+arg_28]
0x18000f0e6  call    ?DistributeStop@@YAXPEAV?$CGenericList@VCAggregateMarshaler@@@@@Z; DistributeStop(CGenericList<CAggregateMarshaler> *)
0x18000f0eb  jmp     short loc_18000F0F7
0x18000f0ed  mov     rcx, [rsp+48h+arg_28]
0x18000f0f2  call    ?DistributePause@@YAXPEAV?$CGenericList@VCAggregateMarshaler@@@@@Z; DistributePause(CGenericList<CAggregateMarshaler> *)
0x18000f0f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0fe  jmp     short loc_18000F102
0x18000f100  xor     ebx, ebx
0x18000f102  cmp     rcx, r15
0x18000f105  jz      short loc_18000F127
0x18000f107  cmp     byte ptr [rcx+19h], 2
0x18000f10b  jb      short loc_18000F127
0x18000f10d  mov     rcx, [rcx+10h]
0x18000f111  mov     edx, 0Fh
0x18000f116  mov     [rsp+48h+var_20], ebx
0x18000f11a  mov     r9, rsi
0x18000f11d  mov     [rsp+48h+var_28], rdi
0x18000f122  call    WPP_SF_qqD
0x18000f127  mov     rbp, [rsp+48h+arg_8]
0x18000f12c  mov     eax, ebx
0x18000f12e  mov     rbx, [rsp+48h+arg_0]
0x18000f133  add     rsp, 30h
0x18000f137  pop     r15
0x18000f139  pop     rdi
0x18000f13a  pop     rsi
0x18000f13b  retn
```
