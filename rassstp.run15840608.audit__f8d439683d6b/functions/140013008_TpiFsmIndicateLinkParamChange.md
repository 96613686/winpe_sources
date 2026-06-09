# TpiFsmIndicateLinkParamChange

- ea: `0x140013008`
- end: `0x14001313d`
- name: `TpiFsmIndicateLinkParamChange`
- size: `309`
- prototype: `__int64 __fastcall(NDIS_HANDLE NdisVcHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400133f0`

## callees

- `0x140002bd8`
- `0x140005e10`
- `0x140006240`
- `0x140013008`

## import_xrefs

- `NDIS!NdisMCoIndicateStatusEx` at `0x1400130e5`
- `NDIS!NdisMCoIndicateStatusEx` at `0x1400130e5`

## pseudocode

```c
void __fastcall TpiFsmIndicateLinkParamChange(
        NDIS_HANDLE NdisVcHandle,
        int a2,
        unsigned __int64 a3,
        unsigned __int64 a4)
{
  struct _NDIS_STATUS_INDICATION StatusIndication; // [rsp+20h] [rbp-69h] BYREF
  __int128 v9; // [rsp+90h] [rbp+7h] BYREF
  int v10; // [rsp+A0h] [rbp+17h]

  v10 = 0;
  v9 = 0;
  memset(&StatusIndication, 0, sizeof(StatusIndication));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  LODWORD(v9) = a2;
  v10 = 4095;
  HIDWORD(v9) = 32;
  StatusIndication.Header = (NDIS_OBJECT_HEADER)7340440;
  DWORD1(v9) = a3 >> 3;
  DWORD2(v9) = a4 >> 3;
  StatusIndication.SourceHandle = (NDIS_HANDLE)*((_QWORD *)SstpGlobals + 21);
  StatusIndication.StatusBuffer = &v9;
  StatusIndication.StatusCode = 1073807397;
  StatusIndication.StatusBufferSize = 20;
  NdisMCoIndicateStatusEx(*((NDIS_HANDLE *)SstpGlobals + 21), NdisVcHandle, &StatusIndication);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
}

```

## disassembly

```asm
0x140013008  push    rbp
0x14001300a  push    rbx
0x14001300b  push    rsi
0x14001300c  push    rdi
0x14001300d  push    r12
0x14001300f  push    r13
0x140013011  push    r14
0x140013013  lea     rbp, [rsp-27h]
0x140013018  sub     rsp, 0B0h
0x14001301f  mov     rax, cs:__security_cookie
0x140013026  xor     rax, rsp
0x140013029  mov     [rbp+57h+var_38], rax
0x14001302d  xor     eax, eax
0x14001302f  mov     rbx, r8
0x140013032  mov     r14d, edx
0x140013035  mov     [rbp+57h+var_40], eax
0x140013038  mov     rsi, rcx
0x14001303b  xorps   xmm0, xmm0
0x14001303e  xor     edx, edx; Val
0x140013040  lea     rcx, [rbp+57h+StatusIndication]; void *
0x140013044  lea     r8d, [rax+70h]; Size
0x140013048  mov     rdi, r9
0x14001304b  movups  [rbp+57h+var_50], xmm0
0x14001304f  call    memset
0x140013054  mov     rcx, cs:WPP_GLOBAL_Control
0x14001305b  lea     r13, WPP_GLOBAL_Control
0x140013062  cmp     rcx, r13
0x140013065  jz      short loc_140013088
0x140013067  mov     eax, [rcx+2Ch]
0x14001306a  and     eax, 82h
0x14001306f  cmp     al, 82h
0x140013071  jnz     short loc_140013088
0x140013073  mov     rcx, [rcx+18h]
0x140013077  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x14001307e  mov     edx, 61h ; 'a'
0x140013083  call    WPP_SF_
0x140013088  mov     rcx, cs:SstpGlobals
0x14001308f  lea     r8, [rbp+57h+StatusIndication]; StatusIndication
0x140013093  mov     dword ptr [rbp+57h+var_50], r14d
0x140013097  mov     rdx, rsi; NdisVcHandle
0x14001309a  mov     [rbp+57h+var_40], 0FFFh
0x1400130a1  mov     dword ptr [rbp+57h+var_50+0Ch], 20h ; ' '
0x1400130a8  mov     dword ptr [rbp+57h+StatusIndication.Header.Type], 700198h
0x1400130af  shr     rbx, 3
0x1400130b3  mov     dword ptr [rbp+57h+var_50+4], ebx
0x1400130b6  shr     rdi, 3
0x1400130ba  mov     dword ptr [rbp+57h+var_50+8], edi
0x1400130bd  mov     rax, [rcx+0A8h]
0x1400130c4  mov     [rbp+57h+StatusIndication.SourceHandle], rax
0x1400130c8  lea     rax, [rbp+57h+var_50]
0x1400130cc  mov     [rbp+57h+StatusIndication.StatusBuffer], rax
0x1400130d0  mov     [rbp+57h+StatusIndication.StatusCode], 40010025h
0x1400130d7  mov     [rbp+57h+StatusIndication.StatusBufferSize], 14h
0x1400130de  mov     rcx, [rcx+0A8h]; MiniportAdapterHandle
0x1400130e5  call    cs:__imp_NdisMCoIndicateStatusEx
0x1400130ec  nop     dword ptr [rax+rax+00h]
0x1400130f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400130f8  cmp     rcx, r13
0x1400130fb  jz      short loc_14001311E
0x1400130fd  mov     eax, [rcx+2Ch]
0x140013100  and     eax, 82h
0x140013105  cmp     al, 82h
0x140013107  jnz     short loc_14001311E
0x140013109  mov     rcx, [rcx+18h]
0x14001310d  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140013114  mov     edx, 62h ; 'b'
0x140013119  call    WPP_SF_
0x14001311e  mov     rcx, [rbp+57h+var_38]
0x140013122  xor     rcx, rsp; StackCookie
0x140013125  call    __security_check_cookie
0x14001312a  add     rsp, 0B0h
0x140013131  pop     r14
0x140013133  pop     r13
0x140013135  pop     r12
0x140013137  pop     rdi
0x140013138  pop     rsi
0x140013139  pop     rbx
0x14001313a  pop     rbp
0x14001313b  retn
```
