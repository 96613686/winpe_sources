# TSPI_lineGetAddressCaps

- ea: `0x180004fe0`
- end: `0x1800051c5`
- name: `TSPI_lineGetAddressCaps`
- size: `485`
- prototype: `LONG __stdcall(DWORD dwDeviceID, DWORD dwAddressID, DWORD dwTSPIVersion, DWORD dwExtVersion, LPLINEADDRESSCAPS lpAddressCaps)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001c7e`
- `0x18000298c`
- `0x18000392c`
- `0x180003980`
- `0x180003af0`
- `0x180004184`
- `0x180004fe0`
- `0x180007df8`

## string_xrefs

- `0x180005014`: `lineGetAddressCaps(%d): deviceID(%x), addressID(%x), TSPIV(%x), ExtV(%x)`

## pseudocode

```c
LONG __stdcall TSPI_lineGetAddressCaps(
        DWORD dwDeviceID,
        DWORD dwAddressID,
        DWORD dwTSPIVersion,
        DWORD dwExtVersion,
        LPLINEADDRESSCAPS lpAddressCaps)
{
  DWORD v8; // eax
  LONG result; // eax
  _DWORD *v10; // rbp
  LONG v11; // esi
  int v12; // eax
  unsigned int v13; // eax
  DWORD dwTotalSize; // eax
  int v15; // [rsp+28h] [rbp-40h]
  void *lpInBuffer; // [rsp+30h] [rbp-38h] BYREF

  TspLog(
    8,
    "lineGetAddressCaps(%d): deviceID(%x), addressID(%x), TSPIV(%x), ExtV(%x)",
    ++dword_18000E248,
    dwDeviceID,
    dwAddressID,
    v15,
    0);
  if ( lpAddressCaps->dwTotalSize < 0xB0 || (v8 = lpAddressCaps->dwTotalSize - 176, v8 + 192 < v8) )
  {
    TspLog(1, "TSPI_lineGetAddressCaps: Arithmatic Overflow error %x", -2147024362);
    return 534;
  }
  else
  {
    result = PrepareSyncRequest(117637386, dwDeviceID, v8 + 192, &lpInBuffer);
    if ( !result )
    {
      v10 = lpInBuffer;
      *((_DWORD *)lpInBuffer + 6) = dwAddressID;
      v10[5] = dwDeviceID;
      v10[7] = dwExtVersion;
      v10[8] = lpAddressCaps->dwTotalSize;
      v10[10] = 176;
      v10[9] = 176;
      memset_0(v10 + 11, 0, 0xA4u);
      v11 = SyncDriverRequest(0x8FFF23C8, v10);
      if ( !v11 )
      {
        v12 = v10[9];
        lpAddressCaps->dwLineDeviceID = dwDeviceID;
        v13 = 2 * v12 - 124;
        lpAddressCaps->dwNeededSize = v13;
        *(_OWORD *)&lpAddressCaps->dwAddressSharing = *((_OWORD *)v10 + 4);
        *(_OWORD *)&lpAddressCaps->dwCalledIDFlags = *((_OWORD *)v10 + 5);
        *(_OWORD *)&lpAddressCaps->dwCallStates = *((_OWORD *)v10 + 6);
        *(_OWORD *)&lpAddressCaps->dwDisconnectModes = *((_OWORD *)v10 + 7);
        *(_OWORD *)&lpAddressCaps->dwMaxNumConference = *((_OWORD *)v10 + 8);
        *(_OWORD *)&lpAddressCaps->dwRemoveFromConfCaps = *((_OWORD *)v10 + 9);
        *(_OWORD *)&lpAddressCaps->dwForwardModes = *((_OWORD *)v10 + 10);
        *(_OWORD *)&lpAddressCaps->dwMaxFwdNumRings = *((_OWORD *)v10 + 11);
        if ( v13 <= lpAddressCaps->dwTotalSize )
        {
          lpAddressCaps->dwUsedSize = 228;
          InsertVarDataString(v10 + 8, v10 + 12, lpAddressCaps, &lpAddressCaps->dwAddressSize);
          InsertVarData(v10 + 8, v10 + 14, lpAddressCaps, &lpAddressCaps->dwDevSpecificSize);
          if ( v10[50] )
          {
            InsertVarData(v10 + 8, v10 + 50, lpAddressCaps, &lpAddressCaps->dwCompletionMsgTextSize);
            lpAddressCaps->dwNumCompletionMessages = v10[48];
            lpAddressCaps->dwCompletionMsgTextEntrySize = v10[49];
          }
          lpAddressCaps->dwNeededSize = lpAddressCaps->dwUsedSize;
        }
        else
        {
          dwTotalSize = 228;
          if ( lpAddressCaps->dwTotalSize < 0xE4 )
            dwTotalSize = lpAddressCaps->dwTotalSize;
          lpAddressCaps->dwUsedSize = dwTotalSize;
        }
        v11 = 0;
      }
      FreeRequest(v10);
      return v11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004fe0  push    rbx
0x180004fe2  push    rbp
0x180004fe3  push    rsi
0x180004fe4  push    rdi
0x180004fe5  push    r14
0x180004fe7  sub     rsp, 40h
0x180004feb  mov     r8d, cs:dword_18000E248
0x180004ff2  mov     esi, r9d
0x180004ff5  inc     r8d
0x180004ff8  mov     [rsp+68h+var_48], edx
0x180004ffc  mov     edi, edx
0x180004ffe  mov     cs:dword_18000E248, r8d
0x180005005  mov     r14d, ecx
0x180005008  mov     [rsp+68h+lpInBuffer], 0
0x180005011  mov     r9d, ecx
0x180005014  lea     rdx, aLinegetaddress_2; "lineGetAddressCaps(%d): deviceID(%x), a"...
0x18000501b  mov     ecx, 8
0x180005020  call    TspLog
0x180005025  mov     rbx, [rsp+68h+lpAddressCaps]
0x18000502d  mov     eax, [rbx]
0x18000502f  cmp     eax, 0B0h
0x180005034  jb      loc_18000519D
0x18000503a  add     eax, 0FFFFFF50h
0x18000503f  lea     r8d, [rax+0C0h]
0x180005046  cmp     r8d, eax
0x180005049  jb      loc_18000519D
0x18000504f  lea     r9, [rsp+68h+lpInBuffer]
0x180005054  mov     edx, r14d
0x180005057  mov     ecx, 703010Ah
0x18000505c  call    PrepareSyncRequest
0x180005061  test    eax, eax
0x180005063  jnz     loc_1800051B9
0x180005069  mov     rbp, [rsp+68h+lpInBuffer]
0x18000506e  xor     edx, edx; Val
0x180005070  mov     r8d, 0A4h; Size
0x180005076  mov     [rbp+18h], edi
0x180005079  lea     rdi, [rbp+20h]
0x18000507d  mov     [rbp+14h], r14d
0x180005081  lea     rcx, [rdi+0Ch]; void *
0x180005085  mov     [rbp+1Ch], esi
0x180005088  mov     eax, [rbx]
0x18000508a  mov     [rdi], eax
0x18000508c  mov     dword ptr [rdi+8], 0B0h
0x180005093  mov     dword ptr [rdi+4], 0B0h
0x18000509a  call    memset_0
0x18000509f  mov     rdx, rbp; lpInBuffer
0x1800050a2  mov     ecx, 8FFF23C8h; dwIoControlCode
0x1800050a7  call    SyncDriverRequest
0x1800050ac  mov     esi, eax
0x1800050ae  test    eax, eax
0x1800050b0  jnz     loc_180005191
0x1800050b6  mov     eax, [rdi+4]
0x1800050b9  mov     [rbx+0Ch], r14d
0x1800050bd  lea     eax, ds:0FFFFFFFFFFFFFF84h[rax*2]
0x1800050c4  mov     [rbx+4], eax
0x1800050c7  movups  xmm0, xmmword ptr [rdi+20h]
0x1800050cb  movups  xmmword ptr [rbx+20h], xmm0
0x1800050cf  movups  xmm1, xmmword ptr [rdi+30h]
0x1800050d3  movups  xmmword ptr [rbx+30h], xmm1
0x1800050d7  movups  xmm0, xmmword ptr [rdi+40h]
0x1800050db  movups  xmmword ptr [rbx+40h], xmm0
0x1800050df  movups  xmm1, xmmword ptr [rdi+50h]
0x1800050e3  movups  xmmword ptr [rbx+50h], xmm1
0x1800050e7  movups  xmm0, xmmword ptr [rdi+60h]
0x1800050eb  movups  xmmword ptr [rbx+60h], xmm0
0x1800050ef  movups  xmm1, xmmword ptr [rdi+70h]
0x1800050f3  movups  xmmword ptr [rbx+70h], xmm1
0x1800050f7  movups  xmm0, xmmword ptr [rdi+80h]
0x1800050fe  movups  xmmword ptr [rbx+80h], xmm0
0x180005105  movups  xmm1, xmmword ptr [rdi+90h]
0x18000510c  movups  xmmword ptr [rbx+90h], xmm1
0x180005113  cmp     eax, [rbx]
0x180005115  jbe     short loc_180005126
0x180005117  mov     eax, 0E4h
0x18000511c  cmp     [rbx], eax
0x18000511e  cmovb   eax, [rbx]
0x180005121  mov     [rbx+8], eax
0x180005124  jmp     short loc_18000518F
0x180005126  lea     r9, [rbx+10h]
0x18000512a  mov     dword ptr [rbx+8], 0E4h
0x180005131  lea     rdx, [rdi+10h]
0x180005135  mov     r8, rbx
0x180005138  mov     rcx, rdi
0x18000513b  call    InsertVarDataString
0x180005140  lea     r9, [rbx+18h]
0x180005144  mov     r8, rbx
0x180005147  lea     rdx, [rdi+18h]
0x18000514b  mov     rcx, rdi
0x18000514e  call    InsertVarData
0x180005153  lea     rdx, [rdi+0A8h]
0x18000515a  cmp     dword ptr [rdx], 0
0x18000515d  jz      short loc_180005189
0x18000515f  lea     r9, [rbx+0A8h]
0x180005166  mov     r8, rbx
0x180005169  mov     rcx, rdi
0x18000516c  call    InsertVarData
0x180005171  mov     eax, [rdi+0A0h]
0x180005177  mov     [rbx+0A0h], eax
0x18000517d  mov     eax, [rdi+0A4h]
0x180005183  mov     [rbx+0A4h], eax
0x180005189  mov     eax, [rbx+8]
0x18000518c  mov     [rbx+4], eax
0x18000518f  xor     esi, esi
0x180005191  mov     rcx, rbp; void *
0x180005194  call    FreeRequest
0x180005199  mov     eax, esi
0x18000519b  jmp     short loc_1800051B9
0x18000519d  mov     r8d, 80070216h
0x1800051a3  lea     rdx, aTspiLinegetadd_2; "TSPI_lineGetAddressCaps: Arithmatic Ove"...
0x1800051aa  mov     ecx, 1
0x1800051af  call    TspLog
0x1800051b4  mov     eax, 216h
0x1800051b9  add     rsp, 40h
0x1800051bd  pop     r14
0x1800051bf  pop     rdi
0x1800051c0  pop     rsi
0x1800051c1  pop     rbp
0x1800051c2  pop     rbx
0x1800051c3  retn
```
