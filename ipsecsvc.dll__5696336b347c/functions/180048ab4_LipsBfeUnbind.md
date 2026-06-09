# LipsBfeUnbind

- ea: `0x180048ab4`
- end: `0x180048bc7`
- name: `LipsBfeUnbind`
- size: `275`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18004842c`
- `0x180048bd0`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x18000f6ac`
- `0x180048478`
- `0x180048ab4`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180048ae7`
- `ntdll!EtwEventWrite` at `0x180048b15`
- `ntdll!EtwEventWrite` at `0x180048ae7`
- `ntdll!EtwEventWrite` at `0x180048b15`
- `fwpuclnt!FwpmEngineClose0` at `0x180048af4`
- `fwpuclnt!FwpmEngineClose0` at `0x180048af4`

## pseudocode

```c
__int64 LipsBfeUnbind()
{
  DWORD v0; // ebx

  if ( !gLipsBfeEngineHandle )
    goto LABEL_15;
  LipsBfeTransactionAbort();
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_EngineClose_Begin, 0, 0);
  v0 = FwpmEngineClose0(gLipsBfeEngineHandle);
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_EngineClose_End, 0, 0);
  if ( !v0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_47af9f0627fa340f85c21449576885fa_Traceguids,
        "FwpmEngineClose0");
      gLipsBfeEngineHandle = 0;
      return 0;
    }
LABEL_15:
    gLipsBfeEngineHandle = 0;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_47af9f0627fa340f85c21449576885fa_Traceguids, v0);
  gLipsBfeEngineHandle = 0;
  return LipsReportError(v0, "LipsBfeUnbind");
}

```

## disassembly

```asm
0x180048ab4  push    rbx
0x180048ab6  sub     rsp, 20h
0x180048aba  xor     ebx, ebx
0x180048abc  cmp     cs:gLipsBfeEngineHandle, rbx
0x180048ac3  jz      loc_180048BB0
0x180048ac9  call    LipsBfeTransactionAbort
0x180048ace  mov     rcx, cs:g_Provider
0x180048ad5  test    rcx, rcx
0x180048ad8  jz      short loc_180048AED
0x180048ada  xor     r9d, r9d
0x180048add  lea     rdx, IPSEC_BFE_EngineClose_Begin
0x180048ae4  xor     r8d, r8d
0x180048ae7  call    cs:__imp_EtwEventWrite
0x180048aed  mov     rcx, cs:gLipsBfeEngineHandle; engineHandle
0x180048af4  call    cs:__imp_FwpmEngineClose0
0x180048afa  mov     rcx, cs:g_Provider
0x180048b01  mov     ebx, eax
0x180048b03  test    rcx, rcx
0x180048b06  jz      short loc_180048B1B
0x180048b08  xor     r9d, r9d
0x180048b0b  lea     rdx, IPSEC_BFE_EngineClose_End
0x180048b12  xor     r8d, r8d
0x180048b15  call    cs:__imp_EtwEventWrite
0x180048b1b  test    ebx, ebx
0x180048b1d  jz      short loc_180048B6E
0x180048b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180048b26  lea     rax, WPP_GLOBAL_Control
0x180048b2d  cmp     rcx, rax
0x180048b30  jz      short loc_180048B50
0x180048b32  test    byte ptr [rcx+1Ch], 10h
0x180048b36  jz      short loc_180048B50
0x180048b38  mov     rcx, [rcx+10h]
0x180048b3c  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x180048b43  mov     edx, 0Fh
0x180048b48  mov     r9d, ebx
0x180048b4b  call    WPP_SF_d
0x180048b50  mov     cs:gLipsBfeEngineHandle, 0
0x180048b5b  lea     rdx, aLipsbfeunbind; "LipsBfeUnbind"
0x180048b62  mov     ecx, ebx
0x180048b64  add     rsp, 20h
0x180048b68  pop     rbx
0x180048b69  jmp     LipsReportError
0x180048b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180048b75  lea     rax, WPP_GLOBAL_Control
0x180048b7c  cmp     rcx, rax
0x180048b7f  jz      short loc_180048BB0
0x180048b81  test    byte ptr [rcx+1Ch], 4
0x180048b85  jz      short loc_180048BB0
0x180048b87  mov     rcx, [rcx+10h]
0x180048b8b  lea     r9, aFwpmengineclos; "FwpmEngineClose0"
0x180048b92  mov     edx, 10h
0x180048b97  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x180048b9e  call    WPP_SF_s
0x180048ba3  mov     cs:gLipsBfeEngineHandle, 0
0x180048bae  jmp     short loc_180048BBF
0x180048bb0  mov     cs:gLipsBfeEngineHandle, 0
0x180048bbb  test    ebx, ebx
0x180048bbd  jnz     short loc_180048B5B
0x180048bbf  xor     eax, eax
0x180048bc1  add     rsp, 20h
0x180048bc5  pop     rbx
0x180048bc6  retn
```
