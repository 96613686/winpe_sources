# LipsBfeTransactionAbort

- ea: `0x180048478`
- end: `0x180048567`
- name: `LipsBfeTransactionAbort`
- size: `239`
- prototype: `__int64()`
- caller_count: `9`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000b2c8`
- `0x180045344`
- `0x180045808`
- `0x180045c1c`
- `0x18004674c`
- `0x180046bdc`
- `0x180048ab4`
- `0x180049008`
- `0x1800499e4`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x18000f6ac`
- `0x180048478`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800484ae`
- `ntdll!EtwEventWrite` at `0x1800484dc`
- `ntdll!EtwEventWrite` at `0x1800484ae`
- `ntdll!EtwEventWrite` at `0x1800484dc`
- `fwpuclnt!FwpmTransactionAbort0` at `0x1800484bb`
- `fwpuclnt!FwpmTransactionAbort0` at `0x1800484bb`

## pseudocode

```c
__int64 LipsBfeTransactionAbort()
{
  DWORD v0; // ebx

  if ( !gLipsBfeTransactions )
    return 0;
  gLipsBfeTransactions = 0;
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_TransactionAbort_Begin, 0, 0);
  v0 = FwpmTransactionAbort0(gLipsBfeEngineHandle);
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_TransactionAbort_End, 0, 0);
  if ( !v0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_47af9f0627fa340f85c21449576885fa_Traceguids,
        "FwpmTransactionAbort0");
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_47af9f0627fa340f85c21449576885fa_Traceguids, v0);
  return LipsReportError(v0, "LipsBfeTransactionAbort");
}

```

## disassembly

```asm
0x180048478  push    rbx
0x18004847a  sub     rsp, 20h
0x18004847e  cmp     cs:gLipsBfeTransactions, 0
0x180048485  jz      loc_18004855F
0x18004848b  mov     rcx, cs:g_Provider
0x180048492  mov     cs:gLipsBfeTransactions, 0
0x18004849c  test    rcx, rcx
0x18004849f  jz      short loc_1800484B4
0x1800484a1  xor     r9d, r9d
0x1800484a4  lea     rdx, IPSEC_BFE_TransactionAbort_Begin
0x1800484ab  xor     r8d, r8d
0x1800484ae  call    cs:__imp_EtwEventWrite
0x1800484b4  mov     rcx, cs:gLipsBfeEngineHandle; engineHandle
0x1800484bb  call    cs:__imp_FwpmTransactionAbort0
0x1800484c1  mov     rcx, cs:g_Provider
0x1800484c8  mov     ebx, eax
0x1800484ca  test    rcx, rcx
0x1800484cd  jz      short loc_1800484E2
0x1800484cf  xor     r9d, r9d
0x1800484d2  lea     rdx, IPSEC_BFE_TransactionAbort_End
0x1800484d9  xor     r8d, r8d
0x1800484dc  call    cs:__imp_EtwEventWrite
0x1800484e2  test    ebx, ebx
0x1800484e4  jz      short loc_18004852A
0x1800484e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800484ed  lea     rax, WPP_GLOBAL_Control
0x1800484f4  cmp     rcx, rax
0x1800484f7  jz      short loc_180048517
0x1800484f9  test    byte ptr [rcx+1Ch], 10h
0x1800484fd  jz      short loc_180048517
0x1800484ff  mov     rcx, [rcx+10h]
0x180048503  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x18004850a  mov     edx, 14h
0x18004850f  mov     r9d, ebx
0x180048512  call    WPP_SF_d
0x180048517  lea     rdx, aLipsbfetransac_0; "LipsBfeTransactionAbort"
0x18004851e  mov     ecx, ebx
0x180048520  add     rsp, 20h
0x180048524  pop     rbx
0x180048525  jmp     LipsReportError
0x18004852a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048531  lea     rax, WPP_GLOBAL_Control
0x180048538  cmp     rcx, rax
0x18004853b  jz      short loc_18004855F
0x18004853d  test    byte ptr [rcx+1Ch], 4
0x180048541  jz      short loc_18004855F
0x180048543  mov     rcx, [rcx+10h]
0x180048547  lea     r9, aFwpmtransactio; "FwpmTransactionAbort0"
0x18004854e  mov     edx, 15h
0x180048553  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x18004855a  call    WPP_SF_s
0x18004855f  xor     eax, eax
0x180048561  add     rsp, 20h
0x180048565  pop     rbx
0x180048566  retn
```
