# LipsBfeTransactionBegin

- ea: `0x180048570`
- end: `0x1800486a7`
- name: `LipsBfeTransactionBegin`
- size: `311`
- prototype: `__int64()`
- caller_count: `8`
- callee_count: `6`
- tags: `loader_planting`

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

- `0x180009d44`
- `0x18000c4d0`
- `0x18000e510`
- `0x18000f6ac`
- `0x180048570`
- `0x180048bd0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800485ef`
- `ntdll!EtwEventWrite` at `0x18004861f`
- `ntdll!EtwEventWrite` at `0x1800485ef`
- `ntdll!EtwEventWrite` at `0x18004861f`
- `fwpuclnt!FwpmTransactionBegin0` at `0x1800485fe`
- `fwpuclnt!FwpmTransactionBegin0` at `0x1800485fe`

## pseudocode

```c
__int64 LipsBfeTransactionBegin()
{
  unsigned int v0; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx

  v0 = LipsBfeBind();
  if ( v0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_18;
    v2 = 22;
    goto LABEL_5;
  }
  if ( ++gLipsBfeTransactions == 1 )
  {
    if ( g_Provider )
      EtwEventWrite(g_Provider, IPSEC_BFE_TransactionBegin_Begin, 0, 0);
    v0 = FwpmTransactionBegin0(gLipsBfeEngineHandle, 0);
    if ( g_Provider )
      EtwEventWrite(g_Provider, IPSEC_BFE_TransactionBegin_End, 0, 0);
    if ( v0 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_18;
      v2 = 23;
LABEL_5:
      WPP_SF_d(v1[2], v2, WPP_47af9f0627fa340f85c21449576885fa_Traceguids, v0);
      goto LABEL_18;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_47af9f0627fa340f85c21449576885fa_Traceguids,
        "FwpmTransactionBegin0");
  }
LABEL_18:
  LipsBfeUnbindOnFailure(v0);
  if ( v0 )
    return LipsReportError(v0, "LipsBfeTransactionBegin");
  else
    return 0;
}

```

## disassembly

```asm
0x180048570  push    rbx
0x180048572  sub     rsp, 20h
0x180048576  call    LipsBfeBind
0x18004857b  mov     ebx, eax
0x18004857d  test    eax, eax
0x18004857f  jz      short loc_1800485BF
0x180048581  mov     rcx, cs:WPP_GLOBAL_Control
0x180048588  lea     rax, WPP_GLOBAL_Control
0x18004858f  cmp     rcx, rax
0x180048592  jz      loc_180048681
0x180048598  test    byte ptr [rcx+1Ch], 10h
0x18004859c  jz      loc_180048681
0x1800485a2  mov     edx, 16h
0x1800485a7  mov     rcx, [rcx+10h]
0x1800485ab  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x1800485b2  mov     r9d, ebx
0x1800485b5  call    WPP_SF_d
0x1800485ba  jmp     loc_180048681
0x1800485bf  mov     eax, cs:gLipsBfeTransactions
0x1800485c5  inc     eax
0x1800485c7  mov     cs:gLipsBfeTransactions, eax
0x1800485cd  cmp     eax, 1
0x1800485d0  jnz     loc_180048681
0x1800485d6  mov     rcx, cs:g_Provider
0x1800485dd  test    rcx, rcx
0x1800485e0  jz      short loc_1800485F5
0x1800485e2  xor     r9d, r9d
0x1800485e5  lea     rdx, IPSEC_BFE_TransactionBegin_Begin
0x1800485ec  xor     r8d, r8d
0x1800485ef  call    cs:__imp_EtwEventWrite
0x1800485f5  mov     rcx, cs:gLipsBfeEngineHandle; engineHandle
0x1800485fc  xor     edx, edx; flags
0x1800485fe  call    cs:__imp_FwpmTransactionBegin0
0x180048604  mov     rcx, cs:g_Provider
0x18004860b  mov     ebx, eax
0x18004860d  test    rcx, rcx
0x180048610  jz      short loc_180048625
0x180048612  xor     r9d, r9d
0x180048615  lea     rdx, IPSEC_BFE_TransactionBegin_End
0x18004861c  xor     r8d, r8d
0x18004861f  call    cs:__imp_EtwEventWrite
0x180048625  test    ebx, ebx
0x180048627  jz      short loc_18004864C
0x180048629  mov     rcx, cs:WPP_GLOBAL_Control
0x180048630  lea     rax, WPP_GLOBAL_Control
0x180048637  cmp     rcx, rax
0x18004863a  jz      short loc_180048681
0x18004863c  test    byte ptr [rcx+1Ch], 10h
0x180048640  jz      short loc_180048681
0x180048642  mov     edx, 17h
0x180048647  jmp     loc_1800485A7
0x18004864c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048653  lea     rax, WPP_GLOBAL_Control
0x18004865a  cmp     rcx, rax
0x18004865d  jz      short loc_180048681
0x18004865f  test    byte ptr [rcx+1Ch], 4
0x180048663  jz      short loc_180048681
0x180048665  mov     rcx, [rcx+10h]
0x180048669  lea     r9, aFwpmtransactio_0; "FwpmTransactionBegin0"
0x180048670  mov     edx, 18h
0x180048675  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x18004867c  call    WPP_SF_s
0x180048681  mov     ecx, ebx
0x180048683  call    LipsBfeUnbindOnFailure
0x180048688  test    ebx, ebx
0x18004868a  jnz     short loc_180048694
0x18004868c  xor     eax, eax
0x18004868e  add     rsp, 20h
0x180048692  pop     rbx
0x180048693  retn
0x180048694  lea     rdx, aLipsbfetransac; "LipsBfeTransactionBegin"
0x18004869b  mov     ecx, ebx
0x18004869d  add     rsp, 20h
0x1800486a1  pop     rbx
0x1800486a2  jmp     LipsReportError
```
