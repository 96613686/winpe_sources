# CController::CRequestSource::OnRequestComplete(IRequest *,_IASREQUESTSTATUS)

- ea: `0x18000d140`
- end: `0x18000d1b4`
- name: `?OnRequestComplete@CRequestSource@CController@@UEAAJPEAUIRequest@@W4_IASREQUESTSTATUS@@@Z`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800094e4`
- `0x18000d140`
- `0x1800179a4`
- `0x18001d31c`

## string_xrefs

- `0x18000d16b`: `Invalid argument passed to OnRequestComplete method`

## pseudocode

```c
__int64 __fastcall CController::CRequestSource::OnRequestComplete(__int64 a1, struct IRequest *a2)
{
  if ( a2 )
    return CRecvFromPipe::Process(*(CPreProcessor ***)(*(_QWORD *)(a1 + 8) + 80LL), a2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Invalid argument passed to OnRequestComplete method");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000d140  sub     rsp, 28h
0x18000d144  test    rdx, rdx
0x18000d147  jnz     short loc_18000D1A1
0x18000d149  lea     rcx, WPP_GLOBAL_Control
0x18000d150  mov     rax, cs:WPP_GLOBAL_Control
0x18000d157  cmp     rax, rcx
0x18000d15a  jz      short loc_18000D19A
0x18000d15c  cmp     byte ptr [rax+19h], 2
0x18000d160  jb      short loc_18000D19A
0x18000d162  test    dword ptr [rax+1Ch], 100h
0x18000d169  jz      short loc_18000D19A
0x18000d16b  lea     rcx, aInvalidArgumen; "Invalid argument passed to OnRequestCom"...
0x18000d172  call    WppDbgPrint
0x18000d177  mov     edx, 54h ; 'T'
0x18000d17c  lea     r9, aNpsrad; "NPSRAD"
0x18000d183  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000d18a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d191  mov     rcx, [rcx+10h]
0x18000d195  call    WPP_SF_s
0x18000d19a  mov     eax, 80004003h
0x18000d19f  jmp     short loc_18000D1AF
0x18000d1a1  mov     rcx, [rcx+8]
0x18000d1a5  mov     rcx, [rcx+50h]; this
0x18000d1a9  call    ?Process@CRecvFromPipe@@QEAAJPEAUIRequest@@@Z; CRecvFromPipe::Process(IRequest *)
0x18000d1ae  nop
0x18000d1af  add     rsp, 28h
0x18000d1b3  retn
0x18002e91b  push    rbp
0x18002e91d  sub     rsp, 20h
0x18002e921  mov     rbp, rdx
0x18002e924  add     rsp, 20h
0x18002e928  pop     rbp
0x18002e929  retn
```
