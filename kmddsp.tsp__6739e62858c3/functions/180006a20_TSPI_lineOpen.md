# TSPI_lineOpen

- ea: `0x180006a20`
- end: `0x180006d31`
- name: `TSPI_lineOpen`
- size: `785`
- prototype: `LONG __stdcall(DWORD dwDeviceID, HTAPILINE htLine, LPHDRVLINE lphdLine, DWORD dwTSPIVersion, LINEEVENT lpfnEventProc)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001e40`
- `0x1800021ac`
- `0x180002930`
- `0x18000298c`
- `0x180002ad0`
- `0x180003af0`
- `0x180004184`
- `0x180006a20`
- `0x180007df8`
- `0x18000809d`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180006aee`
- `KERNEL32!LocalAlloc` at `0x180006aee`
- `KERNEL32!LeaveCriticalSection` at `0x180006abd`
- `KERNEL32!LeaveCriticalSection` at `0x180006b13`
- `KERNEL32!LeaveCriticalSection` at `0x180006ce2`
- `KERNEL32!LeaveCriticalSection` at `0x180006cfb`
- `KERNEL32!LeaveCriticalSection` at `0x180006abd`
- `KERNEL32!LeaveCriticalSection` at `0x180006b13`
- `KERNEL32!LeaveCriticalSection` at `0x180006ce2`
- `KERNEL32!LeaveCriticalSection` at `0x180006cfb`
- `KERNEL32!EnterCriticalSection` at `0x180006a97`
- `KERNEL32!EnterCriticalSection` at `0x180006cbf`
- `KERNEL32!EnterCriticalSection` at `0x180006a97`
- `KERNEL32!EnterCriticalSection` at `0x180006cbf`

## string_xrefs

- `0x180006ca9`: `CommitNegotiatedTSPIVersion: deviceID(%x)`
- `0x180006a64`: `lineOpen(%d): deviceID(%x), htLine(%p)`
- `0x180006ace`: `lineOpen: failed to create line obj`
- `0x180006b82`: `lineOpen: failed to map obj(%p) to handle`
- `0x180006bde`: `lineOpen: obj(%p)`

## pseudocode

```c
LONG __stdcall TSPI_lineOpen(
        DWORD dwDeviceID,
        HTAPILINE htLine,
        LPHDRVLINE lphdLine,
        DWORD dwTSPIVersion,
        LINEEVENT lpfnEventProc)
{
  _DWORD *v7; // r12
  LONG v9; // edi
  _QWORD *v10; // r13
  LONG v11; // ebx
  HDRVLINE v12; // rdi
  __int64 LineDevNode; // rax
  int v14; // eax
  HDRVLINE v15; // [rsp+70h] [rbp-48h] BYREF
  void *lpInBuffer; // [rsp+78h] [rbp-40h] BYREF

  v15 = 0;
  lpInBuffer = 0;
  TspLog(8, "lineOpen(%d): deviceID(%x), htLine(%p)", ++dword_18000E23C, dwDeviceID, htLine);
  if ( !(_DWORD)dword_18000E310 )
    LODWORD(dword_18000E310) = 56;
  EnterCriticalSection(&stru_18000E320);
  v7 = qword_18000E318;
  if ( qword_18000E318 )
  {
    qword_18000E318 = *(HLOCAL *)qword_18000E318;
  }
  else
  {
    v7 = LocalAlloc(0x40u, 0x38u);
    if ( !v7 )
    {
      TspLog(1, "AllocLineObj: failed to alloc a line obj");
      LeaveCriticalSection(&stru_18000E320);
      goto LABEL_6;
    }
  }
  LeaveCriticalSection(&stru_18000E320);
  if ( !v7 )
  {
LABEL_6:
    TspLog(1, "lineOpen: failed to create line obj");
    return -2147483580;
  }
  *v7 = 1263290702;
  v7[1] = dwDeviceID;
  *((_QWORD *)v7 + 1) = htLine;
  v9 = PrepareSyncRequest(117637399, dwDeviceID, 0x2Cu, &lpInBuffer);
  if ( v9 )
  {
    FreeLineObj(v7);
    return v9;
  }
  else
  {
    v10 = lpInBuffer;
    *((_DWORD *)lpInBuffer + 5) = dwDeviceID;
    v11 = OpenObjHandle((__int64)v7, (__int64)FreeLineObj, &v15);
    if ( v11 )
    {
      TspLog(1, "lineOpen: failed to map obj(%p) to handle", v7);
      FreeLineObj(v7);
    }
    else
    {
      v12 = v15;
      v10[3] = v15;
      v11 = SyncDriverRequest(0x8FFF23C8, v10);
      if ( v11 )
      {
        CloseObjHandle(v12);
      }
      else
      {
        memmove_0(v7 + 8, v10 + 5, 0x10u);
        v7[12] = *((_DWORD *)v10 + 14);
        TspLog(4, "lineOpen: obj(%p)", v12);
        TspLog(
          4,
          "Guid: %4.4x-%4.4x-%2.2x%2.2x-%1.1x%1.1x%1.1x%1.1x%1.1x%1.1x%1.1x",
          v7[8],
          *((unsigned __int16 *)v7 + 18),
          *((unsigned __int16 *)v7 + 19),
          *((unsigned __int8 *)v7 + 40),
          *((unsigned __int8 *)v7 + 41),
          *((unsigned __int8 *)v7 + 42),
          *((unsigned __int8 *)v7 + 43),
          *((unsigned __int8 *)v7 + 44),
          *((unsigned __int8 *)v7 + 45),
          *((unsigned __int8 *)v7 + 46),
          *((unsigned __int8 *)v7 + 47));
        TspLog(4, "MediaType(%ld)", v7[12]);
        *((_QWORD *)v7 + 2) = v10[4];
        *lphdLine = v15;
        TspLog(8, "CommitNegotiatedTSPIVersion: deviceID(%x)", dwDeviceID);
        EnterCriticalSection(&stru_18000E3B0);
        LineDevNode = GetLineDevNode(dwDeviceID);
        if ( LineDevNode )
        {
          *(_DWORD *)(LineDevNode + 24) = *(_DWORD *)(LineDevNode + 20);
          LeaveCriticalSection(&stru_18000E3B0);
          v14 = 0;
        }
        else
        {
          LeaveCriticalSection(&stru_18000E3B0);
          v14 = -2147483580;
        }
        v11 = v14;
      }
    }
    FreeRequest(v10);
    return v11;
  }
}

```

## disassembly

```asm
0x180006a20  mov     rax, rsp
0x180006a23  mov     [rax+10h], rbx
0x180006a27  mov     [rax+18h], r8
0x180006a2b  mov     [rax+8], ecx
0x180006a2e  push    rbp
0x180006a2f  push    rsi
0x180006a30  push    rdi
0x180006a31  push    r12
0x180006a33  push    r13
0x180006a35  push    r14
0x180006a37  push    r15
0x180006a39  sub     rsp, 80h
0x180006a40  mov     r8d, cs:dword_18000E23C
0x180006a47  xor     esi, esi
0x180006a49  mov     rdi, rdx
0x180006a4c  mov     [rsp+0B8h+var_98], rdx
0x180006a51  mov     ebx, ecx
0x180006a53  mov     [rax-48h], rsi
0x180006a57  mov     r9d, ecx
0x180006a5a  mov     [rax-40h], rsi
0x180006a5e  lea     ebp, [rsi+1]
0x180006a61  add     r8d, ebp
0x180006a64  lea     rdx, aLineopenDDevic; "lineOpen(%d): deviceID(%x), htLine(%p)"
0x180006a6b  lea     ecx, [rsi+8]
0x180006a6e  mov     cs:dword_18000E23C, r8d
0x180006a75  call    TspLog
0x180006a7a  cmp     cs:dword_18000E310, esi
0x180006a80  lea     r15d, [rsi+38h]
0x180006a84  jnz     short loc_180006A8D
0x180006a86  mov     cs:dword_18000E310, r15d
0x180006a8d  lea     r14, stru_18000E320
0x180006a94  mov     rcx, r14; lpCriticalSection
0x180006a97  call    cs:__imp_EnterCriticalSection
0x180006a9e  nop     dword ptr [rax+rax+00h]
0x180006aa3  mov     r12, cs:qword_18000E318
0x180006aaa  test    r12, r12
0x180006aad  jz      short loc_180006AE6
0x180006aaf  mov     rax, [r12]
0x180006ab3  mov     cs:qword_18000E318, rax
0x180006aba  mov     rcx, r14; lpCriticalSection
0x180006abd  call    cs:__imp_LeaveCriticalSection
0x180006ac4  nop     dword ptr [rax+rax+00h]
0x180006ac9  test    r12, r12
0x180006acc  jnz     short loc_180006B21
0x180006ace  lea     rdx, aLineopenFailed_0; "lineOpen: failed to create line obj"
0x180006ad5  mov     ecx, ebp
0x180006ad7  call    TspLog
0x180006adc  mov     eax, 80000044h
0x180006ae1  jmp     loc_180006D15
0x180006ae6  mov     rdx, r15; uBytes
0x180006ae9  mov     ecx, 40h ; '@'; uFlags
0x180006aee  call    cs:__imp_LocalAlloc
0x180006af5  nop     dword ptr [rax+rax+00h]
0x180006afa  mov     r12, rax
0x180006afd  test    rax, rax
0x180006b00  jnz     short loc_180006ABA
0x180006b02  lea     rdx, aAlloclineobjFa; "AllocLineObj: failed to alloc a line ob"...
0x180006b09  mov     ecx, ebp
0x180006b0b  call    TspLog
0x180006b10  mov     rcx, r14; lpCriticalSection
0x180006b13  call    cs:__imp_LeaveCriticalSection
0x180006b1a  nop     dword ptr [rax+rax+00h]
0x180006b1f  jmp     short loc_180006ACE
0x180006b21  lea     r9, [rsp+0B8h+lpInBuffer]
0x180006b26  mov     dword ptr [r12], 4B4C494Eh
0x180006b2e  mov     r8d, 2Ch ; ','
0x180006b34  mov     [r12+4], ebx
0x180006b39  mov     edx, ebx
0x180006b3b  mov     [r12+8], rdi
0x180006b40  mov     ecx, 7030117h
0x180006b45  call    PrepareSyncRequest
0x180006b4a  mov     edi, eax
0x180006b4c  mov     rcx, r12
0x180006b4f  test    eax, eax
0x180006b51  jz      short loc_180006B5F
0x180006b53  call    FreeLineObj
0x180006b58  mov     eax, edi
0x180006b5a  jmp     loc_180006D15
0x180006b5f  mov     r13, [rsp+0B8h+lpInBuffer]
0x180006b64  lea     r8, [rsp+0B8h+var_48]
0x180006b69  lea     rdx, FreeLineObj
0x180006b70  mov     [r13+14h], ebx
0x180006b74  call    OpenObjHandle
0x180006b79  mov     ebx, eax
0x180006b7b  test    eax, eax
0x180006b7d  jz      short loc_180006B9D
0x180006b7f  mov     r8, r12
0x180006b82  lea     rdx, aLineopenFailed; "lineOpen: failed to map obj(%p) to hand"...
0x180006b89  mov     ecx, ebp
0x180006b8b  call    TspLog
0x180006b90  mov     rcx, r12
0x180006b93  call    FreeLineObj
0x180006b98  jmp     loc_180006D0B
0x180006b9d  mov     rdi, [rsp+0B8h+var_48]
0x180006ba2  mov     rdx, r13; lpInBuffer
0x180006ba5  mov     ecx, 8FFF23C8h; dwIoControlCode
0x180006baa  mov     [r13+18h], rdi
0x180006bae  call    SyncDriverRequest
0x180006bb3  mov     ebx, eax
0x180006bb5  test    eax, eax
0x180006bb7  jz      short loc_180006BC6
0x180006bb9  mov     rcx, rdi
0x180006bbc  call    CloseObjHandle
0x180006bc1  jmp     loc_180006D0B
0x180006bc6  mov     r8d, 10h; Size
0x180006bcc  lea     rdx, [r13+28h]; Src
0x180006bd0  lea     rcx, [r12+20h]; void *
0x180006bd5  call    memmove_0
0x180006bda  mov     eax, [r13+38h]
0x180006bde  lea     rdx, aLineopenObjP; "lineOpen: obj(%p)"
0x180006be5  mov     r8, rdi
0x180006be8  mov     [r12+30h], eax
0x180006bed  mov     ecx, 4
0x180006bf2  call    TspLog
0x180006bf7  movzx   edx, byte ptr [r12+2Eh]
0x180006bfd  movzx   ebx, byte ptr [r12+2Bh]
0x180006c03  movzx   eax, byte ptr [r12+2Fh]
0x180006c09  movzx   r10d, byte ptr [r12+2Dh]
0x180006c0f  movzx   r11d, byte ptr [r12+2Ch]
0x180006c15  movzx   edi, byte ptr [r12+2Ah]
0x180006c1b  movzx   esi, byte ptr [r12+29h]
0x180006c21  movzx   ebp, byte ptr [r12+28h]
0x180006c27  movzx   r14d, word ptr [r12+26h]
0x180006c2d  movzx   r9d, word ptr [r12+24h]
0x180006c33  mov     r8d, [r12+20h]
0x180006c38  mov     [rsp+0B8h+var_58], eax
0x180006c3c  mov     [rsp+0B8h+var_60], edx
0x180006c40  lea     rdx, aGuid44x44x22x2; "Guid: %4.4x-%4.4x-%2.2x%2.2x-%1.1x%1.1x"...
0x180006c47  mov     [rsp+0B8h+var_68], r10d
0x180006c4c  mov     [rsp+0B8h+var_70], r11d
0x180006c51  mov     [rsp+0B8h+var_78], ebx
0x180006c55  mov     ebx, 4
0x180006c5a  mov     [rsp+0B8h+var_80], edi
0x180006c5e  mov     ecx, ebx
0x180006c60  mov     [rsp+0B8h+var_88], esi
0x180006c64  mov     [rsp+0B8h+var_90], ebp
0x180006c68  mov     dword ptr [rsp+0B8h+var_98], r14d
0x180006c6d  call    TspLog
0x180006c72  mov     r8d, [r12+30h]
0x180006c77  lea     rdx, aMediatypeLd; "MediaType(%ld)"
0x180006c7e  mov     ecx, ebx
0x180006c80  call    TspLog
0x180006c85  mov     rax, [r13+20h]
0x180006c89  lea     ecx, [rbx+4]
0x180006c8c  mov     rdx, [rsp+0B8h+arg_10]
0x180006c94  mov     r8d, [rsp+0B8h+arg_0]
0x180006c9c  mov     [r12+10h], rax
0x180006ca1  mov     rax, [rsp+0B8h+var_48]
0x180006ca6  mov     [rdx], rax
0x180006ca9  lea     rdx, aCommitnegotiat; "CommitNegotiatedTSPIVersion: deviceID(%"...
0x180006cb0  call    TspLog
0x180006cb5  lea     rdi, stru_18000E3B0
0x180006cbc  mov     rcx, rdi; lpCriticalSection
0x180006cbf  call    cs:__imp_EnterCriticalSection
0x180006cc6  nop     dword ptr [rax+rax+00h]
0x180006ccb  mov     ecx, [rsp+0B8h+arg_0]
0x180006cd2  call    GetLineDevNode
0x180006cd7  mov     rdx, rax
0x180006cda  mov     rcx, rdi; lpCriticalSection
0x180006cdd  test    rax, rax
0x180006ce0  jnz     short loc_180006CF5
0x180006ce2  call    cs:__imp_LeaveCriticalSection
0x180006ce9  nop     dword ptr [rax+rax+00h]
0x180006cee  mov     eax, 80000044h
0x180006cf3  jmp     short loc_180006D09
0x180006cf5  mov     eax, [rax+14h]
0x180006cf8  mov     [rdx+18h], eax
0x180006cfb  call    cs:__imp_LeaveCriticalSection
0x180006d02  nop     dword ptr [rax+rax+00h]
0x180006d07  xor     eax, eax
0x180006d09  mov     ebx, eax
0x180006d0b  mov     rcx, r13; void *
0x180006d0e  call    FreeRequest
0x180006d13  mov     eax, ebx
0x180006d15  mov     rbx, [rsp+0B8h+arg_8]
0x180006d1d  add     rsp, 80h
0x180006d24  pop     r15
0x180006d26  pop     r14
0x180006d28  pop     r13
0x180006d2a  pop     r12
0x180006d2c  pop     rdi
0x180006d2d  pop     rsi
0x180006d2e  pop     rbp
0x180006d2f  retn
```
