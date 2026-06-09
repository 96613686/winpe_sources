# LipsBfeTransactionCommit

- ea: `0x1800486b0`
- end: `0x1800487a4`
- name: `LipsBfeTransactionCommit`
- size: `244`
- prototype: `__int64()`
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b2c8`
- `0x180045344`
- `0x180045808`
- `0x180045c1c`
- `0x18004674c`
- `0x180046bdc`
- `0x180049008`
- `0x1800499e4`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x18000f6ac`
- `0x1800486b0`
- `0x180048bd0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800486de`
- `ntdll!EtwEventWrite` at `0x18004870c`
- `ntdll!EtwEventWrite` at `0x1800486de`
- `ntdll!EtwEventWrite` at `0x18004870c`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800486eb`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800486eb`

## string_xrefs

- `0x180048766`: `FwpmTransactionCommit0`
- `0x180048791`: `LipsBfeTransactionCommit`

## pseudocode

```c
__int64 LipsBfeTransactionCommit()
{
  DWORD v0; // ebx

  v0 = 0;
  if ( !--gLipsBfeTransactions )
  {
    if ( g_Provider )
      EtwEventWrite(g_Provider, IPSEC_BFE_TransactionCommit_Begin, 0, 0);
    v0 = FwpmTransactionCommit0(gLipsBfeEngineHandle);
    if ( g_Provider )
      EtwEventWrite(g_Provider, IPSEC_BFE_TransactionCommit_End, 0, 0);
    if ( v0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_47af9f0627fa340f85c21449576885fa_Traceguids, v0);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_47af9f0627fa340f85c21449576885fa_Traceguids,
        "FwpmTransactionCommit0");
    }
  }
  LipsBfeUnbindOnFailure(v0);
  if ( v0 )
    return LipsReportError(v0, "LipsBfeTransactionCommit");
  else
    return 0;
}

```

## disassembly

```asm
0x1800486b0  push    rbx
0x1800486b2  sub     rsp, 20h
0x1800486b6  xor     ebx, ebx
0x1800486b8  add     cs:gLipsBfeTransactions, 0FFFFFFFFh
0x1800486bf  jnz     loc_18004877E
0x1800486c5  mov     rcx, cs:g_Provider
0x1800486cc  test    rcx, rcx
0x1800486cf  jz      short loc_1800486E4
0x1800486d1  xor     r9d, r9d
0x1800486d4  lea     rdx, IPSEC_BFE_TransactionCommit_Begin
0x1800486db  xor     r8d, r8d
0x1800486de  call    cs:__imp_EtwEventWrite
0x1800486e4  mov     rcx, cs:gLipsBfeEngineHandle; engineHandle
0x1800486eb  call    cs:__imp_FwpmTransactionCommit0
0x1800486f1  mov     rcx, cs:g_Provider
0x1800486f8  mov     ebx, eax
0x1800486fa  test    rcx, rcx
0x1800486fd  jz      short loc_180048712
0x1800486ff  xor     r9d, r9d
0x180048702  lea     rdx, IPSEC_BFE_TransactionCommit_End
0x180048709  xor     r8d, r8d
0x18004870c  call    cs:__imp_EtwEventWrite
0x180048712  test    ebx, ebx
0x180048714  jz      short loc_180048749
0x180048716  mov     rcx, cs:WPP_GLOBAL_Control
0x18004871d  lea     rax, WPP_GLOBAL_Control
0x180048724  cmp     rcx, rax
0x180048727  jz      short loc_18004877E
0x180048729  test    byte ptr [rcx+1Ch], 10h
0x18004872d  jz      short loc_18004877E
0x18004872f  mov     rcx, [rcx+10h]
0x180048733  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x18004873a  mov     edx, 19h
0x18004873f  mov     r9d, ebx
0x180048742  call    WPP_SF_d
0x180048747  jmp     short loc_18004877E
0x180048749  mov     rcx, cs:WPP_GLOBAL_Control
0x180048750  lea     rax, WPP_GLOBAL_Control
0x180048757  cmp     rcx, rax
0x18004875a  jz      short loc_18004877E
0x18004875c  test    byte ptr [rcx+1Ch], 4
0x180048760  jz      short loc_18004877E
0x180048762  mov     rcx, [rcx+10h]
0x180048766  lea     r9, aFwpmtransactio_1; "FwpmTransactionCommit0"
0x18004876d  mov     edx, 1Ah
0x180048772  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x180048779  call    WPP_SF_s
0x18004877e  mov     ecx, ebx
0x180048780  call    LipsBfeUnbindOnFailure
0x180048785  test    ebx, ebx
0x180048787  jnz     short loc_180048791
0x180048789  xor     eax, eax
0x18004878b  add     rsp, 20h
0x18004878f  pop     rbx
0x180048790  retn
0x180048791  lea     rdx, aLipsbfetransac_1; "LipsBfeTransactionCommit"
0x180048798  mov     ecx, ebx
0x18004879a  add     rsp, 20h
0x18004879e  pop     rbx
0x18004879f  jmp     LipsReportError
```
