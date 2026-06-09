# RtdsRegisterUpdateCallback

- ea: `0x14000a320`
- end: `0x14000a453`
- name: `RtdsRegisterUpdateCallback`
- size: `307`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000b080`

## callees

- `0x140001760`
- `0x140001780`
- `0x14000a320`

## import_xrefs

- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14000a3fb`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14000a3fb`

## pseudocode

```c
__int64 RtdsRegisterUpdateCallback()
{
  unsigned int i; // edx
  __int64 v1; // rbx
  __int64 *v2; // r8
  __int64 v3; // rax
  __int64 v4; // rdi
  struct _KMUTANT *v5; // rcx
  struct _KMUTANT *v7; // rcx

  for ( i = 0; ; ++i )
  {
    if ( i >= 2 )
      return 3221226021LL;
    v1 = 2LL * i;
    v2 = (__int64 *)(&off_140004000)[2 * i];
    v3 = NAMED_PIPE_EVENT_GUID - *v2;
    if ( NAMED_PIPE_EVENT_GUID == *v2 )
      v3 = 0x554B2F0C7B7E0C9ELL - v2[1];
    if ( !v3 )
      break;
  }
  v4 = 7LL * i;
  RtdspLock((&off_1400050D0)[v4]);
  v5 = (struct _KMUTANT *)(&off_1400050D0)[v4];
  if ( qword_1400050B8[v4] )
  {
    RtdspUnlock(v5);
    return 3221225485LL;
  }
  else
  {
    qword_1400050B8[v4] = (__int64)NptrigTriggerChangeCallback;
    RtdspUnlock(v5);
    if ( (int)ExSubscribeWnfStateChange(
                &RtdsProviderWnfState[v4 + 4],
                off_140004008[v1],
                1,
                0,
                RtdsInternalUpdateCallback,
                &RtdsProviderWnfState[v4]) >= 0 )
    {
      return 0;
    }
    else
    {
      RtdspLock((&off_1400050D0)[v4]);
      v7 = (struct _KMUTANT *)(&off_1400050D0)[v4];
      qword_1400050B8[v4] = 0;
      RtdspUnlock(v7);
      return 3221225473LL;
    }
  }
}

```

## disassembly

```asm
0x14000a320  push    rsi
0x14000a322  sub     rsp, 30h
0x14000a326  mov     r10, cs:qword_1400041B8
0x14000a32d  lea     rsi, cs:140000000h
0x14000a334  mov     r11, cs:NAMED_PIPE_EVENT_GUID
0x14000a33b  xor     edx, edx
0x14000a33d  mov     [rsp+38h+arg_0], rbx
0x14000a342  cmp     edx, 2
0x14000a345  jnb     loc_14000A442
0x14000a34b  mov     ebx, edx
0x14000a34d  mov     rax, r11
0x14000a350  add     rbx, rbx
0x14000a353  mov     r9d, edx
0x14000a356  mov     r8, ds:rva off_140004000[rsi+rbx*8]
0x14000a35e  sub     rax, [r8]
0x14000a361  jnz     short loc_14000A36A
0x14000a363  mov     rax, r10
0x14000a366  sub     rax, [r8+8]
0x14000a36a  test    rax, rax
0x14000a36d  jz      short loc_14000A373
0x14000a36f  inc     edx
0x14000a371  jmp     short loc_14000A342
0x14000a373  mov     [rsp+38h+arg_8], rdi
0x14000a378  imul    rdi, r9, 38h ; '8'
0x14000a37c  mov     rcx, [rdi+rsi+50D0h]
0x14000a384  call    RtdspLock
0x14000a389  cmp     qword ptr [rdi+rsi+50B8h], 0
0x14000a392  mov     rcx, [rdi+rsi+50D0h]
0x14000a39a  jz      short loc_14000A3B7
0x14000a39c  call    RtdspUnlock
0x14000a3a1  mov     eax, 0C000000Dh
0x14000a3a6  mov     rdi, [rsp+38h+arg_8]
0x14000a3ab  mov     rbx, [rsp+38h+arg_0]
0x14000a3b0  add     rsp, 30h
0x14000a3b4  pop     rsi
0x14000a3b5  retn
0x14000a3b7  lea     rax, NptrigTriggerChangeCallback
0x14000a3be  mov     [rdi+rsi+50B8h], rax
0x14000a3c6  call    RtdspUnlock
0x14000a3cb  mov     rdx, ds:rva off_140004008[rsi+rbx*8]
0x14000a3d3  lea     rax, rva RtdsProviderWnfState[rsi]
0x14000a3da  add     rax, rdi
0x14000a3dd  xor     r9d, r9d
0x14000a3e0  mov     [rsp+38h+var_10], rax
0x14000a3e5  mov     r8d, 1
0x14000a3eb  lea     rcx, [rax+20h]
0x14000a3ef  lea     rax, RtdsInternalUpdateCallback
0x14000a3f6  mov     [rsp+38h+var_18], rax
0x14000a3fb  call    cs:__imp_ExSubscribeWnfStateChange
0x14000a402  nop     dword ptr [rax+rax+00h]
0x14000a407  test    eax, eax
0x14000a409  jns     short loc_14000A43B
0x14000a40b  mov     rcx, [rdi+rsi+50D0h]
0x14000a413  call    RtdspLock
0x14000a418  mov     rcx, [rdi+rsi+50D0h]
0x14000a420  mov     qword ptr [rdi+rsi+50B8h], 0
0x14000a42c  call    RtdspUnlock
0x14000a431  mov     eax, 0C0000001h
0x14000a436  jmp     loc_14000A3A6
0x14000a43b  xor     eax, eax
0x14000a43d  jmp     loc_14000A3A6
0x14000a442  mov     rbx, [rsp+38h+arg_0]
0x14000a447  mov     eax, 0C0000225h
0x14000a44c  add     rsp, 30h
0x14000a450  pop     rsi
0x14000a451  retn
```
