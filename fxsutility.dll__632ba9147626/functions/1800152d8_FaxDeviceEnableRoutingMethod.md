# FaxDeviceEnableRoutingMethod

- ea: `0x1800152d8`
- end: `0x1800154a3`
- name: `FaxDeviceEnableRoutingMethod`
- size: `459`
- prototype: `__int64 __fastcall(HANDLE FaxHandle, DWORD DeviceId, LPCWSTR RoutingGuid)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010bc8`
- `0x180011f58`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x1800152d8`

## import_xrefs

- `FXSAPI!FaxGetRoutingInfoW` at `0x1800153b6`
- `FXSAPI!FaxGetRoutingInfoW` at `0x1800153b6`
- `FXSAPI!FaxOpenPort` at `0x180015364`
- `FXSAPI!FaxOpenPort` at `0x180015364`
- `FXSAPI!FaxClose` at `0x18001548e`
- `FXSAPI!FaxClose` at `0x18001548e`
- `FXSAPI!FaxFreeBuffer` at `0x18001547f`
- `FXSAPI!FaxFreeBuffer` at `0x18001547f`
- `FXSAPI!FaxSetRoutingInfoW` at `0x180015421`
- `FXSAPI!FaxSetRoutingInfoW` at `0x180015421`
- `KERNEL32!SetLastError` at `0x180015347`
- `KERNEL32!SetLastError` at `0x180015347`
- `KERNEL32!GetLastError` at `0x180015399`
- `KERNEL32!GetLastError` at `0x1800153eb`
- `KERNEL32!GetLastError` at `0x180015451`
- `KERNEL32!GetLastError` at `0x180015399`
- `KERNEL32!GetLastError` at `0x1800153eb`
- `KERNEL32!GetLastError` at `0x180015451`

## pseudocode

```c
__int64 __fastcall FaxDeviceEnableRoutingMethod(HANDLE FaxHandle, DWORD DeviceId, LPCWSTR RoutingGuid, int a4)
{
  unsigned int v9; // ebx
  DWORD LastError; // eax
  __int64 v11; // rdx
  LPBYTE RoutingInfoBuffer; // [rsp+20h] [rbp-18h] BYREF
  HANDLE FaxPortHandle; // [rsp+28h] [rbp-10h] BYREF
  DWORD RoutingInfoBufferSize; // [rsp+70h] [rbp+38h] BYREF

  FaxPortHandle = 0;
  RoutingInfoBuffer = 0;
  RoutingInfoBufferSize = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_df13447c5ef0313a58847de557c35443_Traceguids);
  }
  if ( !FaxHandle )
  {
    SetLastError(0x57u);
    return 0;
  }
  v9 = 0;
  if ( !FaxOpenPort(FaxHandle, DeviceId, 3u, &FaxPortHandle) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    LastError = GetLastError();
    v11 = 11;
    goto LABEL_25;
  }
  if ( !FaxGetRoutingInfoW(FaxPortHandle, RoutingGuid, &RoutingInfoBuffer, &RoutingInfoBufferSize) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    LastError = GetLastError();
    v11 = 12;
    goto LABEL_25;
  }
  if ( a4 == -1 )
  {
    LOBYTE(v9) = *(_DWORD *)RoutingInfoBuffer != 0;
  }
  else
  {
    *(_DWORD *)RoutingInfoBuffer = a4 == 1;
    if ( !FaxSetRoutingInfoW(FaxPortHandle, RoutingGuid, RoutingInfoBuffer, RoutingInfoBufferSize) )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_26;
      }
      LastError = GetLastError();
      v11 = 13;
LABEL_25:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_df13447c5ef0313a58847de557c35443_Traceguids, LastError);
      goto LABEL_26;
    }
    v9 = 1;
  }
LABEL_26:
  if ( RoutingInfoBuffer )
    FaxFreeBuffer(RoutingInfoBuffer);
  if ( FaxPortHandle )
    FaxClose(FaxPortHandle);
  return v9;
}

```

## disassembly

```asm
0x1800152d8  push    rbp
0x1800152da  push    rbx
0x1800152db  push    rsi
0x1800152dc  push    rdi
0x1800152dd  push    r14
0x1800152df  push    r15
0x1800152e1  mov     rbp, rsp
0x1800152e4  sub     rsp, 38h
0x1800152e8  mov     esi, r9d
0x1800152eb  mov     [rbp+FaxPortHandle], 0
0x1800152f3  mov     r14, r8
0x1800152f6  mov     [rbp+RoutingInfoBuffer], 0
0x1800152fe  mov     r15d, edx
0x180015301  mov     [rbp+RoutingInfoBufferSize], 0
0x180015308  mov     rdi, rcx
0x18001530b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015312  lea     rax, WPP_GLOBAL_Control
0x180015319  cmp     rcx, rax
0x18001531c  jz      short loc_18001533F
0x18001531e  test    byte ptr [rcx+1Ch], 2
0x180015322  jz      short loc_18001533F
0x180015324  cmp     byte ptr [rcx+19h], 5
0x180015328  jb      short loc_18001533F
0x18001532a  mov     rcx, [rcx+10h]
0x18001532e  lea     r8, WPP_df13447c5ef0313a58847de557c35443_Traceguids
0x180015335  mov     edx, 0Ah
0x18001533a  call    WPP_SF_
0x18001533f  test    rdi, rdi
0x180015342  jnz     short loc_180015354
0x180015344  lea     ecx, [rdi+57h]; dwErrCode
0x180015347  call    cs:__imp_SetLastError
0x18001534d  xor     eax, eax
0x18001534f  jmp     loc_180015496
0x180015354  xor     ebx, ebx
0x180015356  lea     r9, [rbp+FaxPortHandle]; FaxPortHandle
0x18001535a  mov     edx, r15d; DeviceId
0x18001535d  mov     rcx, rdi; FaxHandle
0x180015360  lea     r8d, [rbx+3]; Flags
0x180015364  call    cs:__imp_FaxOpenPort
0x18001536a  test    eax, eax
0x18001536c  jnz     short loc_1800153A7
0x18001536e  mov     rax, cs:WPP_GLOBAL_Control
0x180015375  lea     rcx, WPP_GLOBAL_Control
0x18001537c  cmp     rax, rcx
0x18001537f  jz      loc_180015476
0x180015385  test    byte ptr [rax+1Ch], 2
0x180015389  jz      loc_180015476
0x18001538f  cmp     byte ptr [rax+19h], 2
0x180015393  jb      loc_180015476
0x180015399  call    cs:__imp_GetLastError
0x18001539f  lea     edx, [rbx+0Bh]
0x1800153a2  jmp     loc_18001545C
0x1800153a7  mov     rcx, [rbp+FaxPortHandle]; FaxPortHandle
0x1800153ab  lea     r9, [rbp+RoutingInfoBufferSize]; RoutingInfoBufferSize
0x1800153af  lea     r8, [rbp+RoutingInfoBuffer]; RoutingInfoBuffer
0x1800153b3  mov     rdx, r14; RoutingGuid
0x1800153b6  call    cs:__imp_FaxGetRoutingInfoW
0x1800153bc  test    eax, eax
0x1800153be  jnz     short loc_1800153F8
0x1800153c0  mov     rax, cs:WPP_GLOBAL_Control
0x1800153c7  lea     rcx, WPP_GLOBAL_Control
0x1800153ce  cmp     rax, rcx
0x1800153d1  jz      loc_180015476
0x1800153d7  test    byte ptr [rax+1Ch], 2
0x1800153db  jz      loc_180015476
0x1800153e1  cmp     byte ptr [rax+19h], 2
0x1800153e5  jb      loc_180015476
0x1800153eb  call    cs:__imp_GetLastError
0x1800153f1  mov     edx, 0Ch
0x1800153f6  jmp     short loc_18001545C
0x1800153f8  mov     rax, [rbp+RoutingInfoBuffer]
0x1800153fc  cmp     esi, 0FFFFFFFFh
0x1800153ff  jnz     short loc_180015408
0x180015401  cmp     [rax], ebx
0x180015403  setnbe  bl
0x180015406  jmp     short loc_180015476
0x180015408  xor     ecx, ecx
0x18001540a  mov     rdx, r14; RoutingGuid
0x18001540d  cmp     esi, 1
0x180015410  setz    cl
0x180015413  mov     [rax], ecx
0x180015415  mov     r9d, [rbp+RoutingInfoBufferSize]; RoutingInfoBufferSize
0x180015419  mov     r8, [rbp+RoutingInfoBuffer]; RoutingInfoBuffer
0x18001541d  mov     rcx, [rbp+FaxPortHandle]; FaxPortHandle
0x180015421  call    cs:__imp_FaxSetRoutingInfoW
0x180015427  test    eax, eax
0x180015429  jz      short loc_180015432
0x18001542b  mov     ebx, 1
0x180015430  jmp     short loc_180015476
0x180015432  mov     rax, cs:WPP_GLOBAL_Control
0x180015439  lea     rcx, WPP_GLOBAL_Control
0x180015440  cmp     rax, rcx
0x180015443  jz      short loc_180015476
0x180015445  test    byte ptr [rax+1Ch], 2
0x180015449  jz      short loc_180015476
0x18001544b  cmp     byte ptr [rax+19h], 2
0x18001544f  jb      short loc_180015476
0x180015451  call    cs:__imp_GetLastError
0x180015457  mov     edx, 0Dh
0x18001545c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015463  lea     r8, WPP_df13447c5ef0313a58847de557c35443_Traceguids
0x18001546a  mov     r9d, eax
0x18001546d  mov     rcx, [rcx+10h]
0x180015471  call    WPP_SF_d
0x180015476  mov     rcx, [rbp+RoutingInfoBuffer]; Buffer
0x18001547a  test    rcx, rcx
0x18001547d  jz      short loc_180015485
0x18001547f  call    cs:__imp_FaxFreeBuffer
0x180015485  mov     rcx, [rbp+FaxPortHandle]; FaxHandle
0x180015489  test    rcx, rcx
0x18001548c  jz      short loc_180015494
0x18001548e  call    cs:__imp_FaxClose
0x180015494  mov     eax, ebx
0x180015496  add     rsp, 38h
0x18001549a  pop     r15
0x18001549c  pop     r14
0x18001549e  pop     rdi
0x18001549f  pop     rsi
0x1800154a0  pop     rbx
0x1800154a1  pop     rbp
0x1800154a2  retn
```
