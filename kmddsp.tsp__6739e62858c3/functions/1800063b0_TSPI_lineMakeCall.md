# TSPI_lineMakeCall

- ea: `0x1800063b0`
- end: `0x1800066cf`
- name: `TSPI_lineMakeCall`
- size: `799`
- prototype: `LONG __stdcall(DRV_REQUESTID dwRequestID, HDRVLINE hdLine, HTAPICALL htCall, LPHDRVCALL lphdCall, LPCWSTR lpszDestAddress, DWORD dwCountryCode, const LPLINECALLPARAMS lpCallParams)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180001ca4`
- `0x180001e40`
- `0x1800021ac`
- `0x180002494`
- `0x1800026b8`
- `0x1800028d0`
- `0x18000298c`
- `0x180002b6c`
- `0x1800037a8`
- `0x1800039f8`
- `0x1800063b0`
- `0x180007df8`
- `0x180008091`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1800064b7`
- `KERNEL32!WideCharToMultiByte` at `0x180006612`
- `KERNEL32!WideCharToMultiByte` at `0x180006679`
- `KERNEL32!WideCharToMultiByte` at `0x1800064b7`
- `KERNEL32!WideCharToMultiByte` at `0x180006612`
- `KERNEL32!WideCharToMultiByte` at `0x180006679`
- `KERNEL32!lstrlenW` at `0x18000647f`
- `KERNEL32!lstrlenW` at `0x18000647f`

## string_xrefs

- `0x18000642c`: `lineMakeCall: failed to create call obj`
- `0x180006584`: `lineMakeCall: failed to reacquire read lock for obj(%p)`

## pseudocode

```c
LONG __stdcall TSPI_lineMakeCall(
        DRV_REQUESTID dwRequestID,
        HDRVLINE hdLine,
        HTAPICALL htCall,
        LPHDRVCALL lphdCall,
        LPCWSTR lpszDestAddress,
        DWORD dwCountryCode,
        const LPLINECALLPARAMS lpCallParams)
{
  LONG result; // eax
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  LONG Lock; // ebx
  __int64 v14; // rcx
  int v15; // eax
  UINT v16; // r14d
  int v17; // r15d
  int v18; // ebx
  int cbMultiByte; // r15d
  DWORD v20; // eax
  _QWORD *v21; // r13
  HDRVCALL v22; // rdi
  char *v23; // rbx
  DWORD dwOrigAddressSize; // edx
  DWORD v25; // [rsp+40h] [rbp-28h]
  int cchWideChar; // [rsp+44h] [rbp-24h]
  void *v27; // [rsp+48h] [rbp-20h] BYREF
  __int64 v28; // [rsp+50h] [rbp-18h] BYREF
  HDRVCALL v29[2]; // [rsp+58h] [rbp-10h] BYREF

  v28 = 0;
  v29[0] = 0;
  v27 = 0;
  TspLog(8, "lineMakeCall(%d): reqID(%x), line(%p)", ++dword_18000E2A0, dwRequestID, hdLine);
  result = GetLineObjWithReadLock(hdLine, &v28);
  if ( !result )
  {
    v11 = (_DWORD *)AllocCallObj();
    v12 = v11;
    if ( !v11 )
    {
      TspLog(1, "lineMakeCall: failed to create call obj");
      Lock = -2147483580;
      goto LABEL_30;
    }
    v14 = v28;
    *v11 = 1329807692;
    v15 = *(_DWORD *)(v14 + 4);
    v12[16] = 1;
    v16 = 65001;
    v12[1] = v15;
    *((_QWORD *)v12 + 1) = htCall;
    *((_QWORD *)v12 + 4) = hdLine;
    v17 = *(_DWORD *)(v14 + 48);
    if ( v17 != 12 )
      v16 = 0;
    if ( !lpszDestAddress )
    {
      cbMultiByte = 0;
      cchWideChar = 0;
      goto LABEL_13;
    }
    v18 = lstrlenW(lpszDestAddress) + 1;
    cchWideChar = v18;
    if ( v17 == 12 )
    {
      cbMultiByte = WideCharToMultiByte(v16, 0, lpszDestAddress, v18, 0, 0, 0, 0);
      if ( cbMultiByte )
      {
LABEL_11:
        v14 = v28;
LABEL_13:
        if ( lpCallParams )
          v20 = lpCallParams->dwTotalSize - 112;
        else
          v20 = 0;
        v25 = v20;
        Lock = PrepareAsyncRequest(117637397, *(_DWORD *)(v14 + 4), dwRequestID, cbMultiByte + v20 + 160, &v27);
        if ( !Lock )
        {
          ReleaseObjReadLock(hdLine);
          Lock = OpenObjHandle(v12, FreeCallObj, v29);
          if ( Lock )
          {
            TspLog(1, "lineMakeCall: failed to map obj(%p) to handle", v12);
            FreeRequest(v27);
            FreeCallObj(v12);
          }
          else
          {
            Lock = AcquireObjReadLock(hdLine);
            if ( !Lock )
            {
              v21 = v27;
              *((HDRVCALL *)v12 + 2) = v29[0];
              v22 = v29[0];
              v23 = (char *)(v21 + 15);
              v21[16] = *(_QWORD *)(v28 + 16);
              v21[17] = v22;
              *((_DWORD *)v21 + 38) = cbMultiByte;
              if ( lpszDestAddress )
              {
                *((_DWORD *)v21 + 39) = v25 + 160;
                WideCharToMultiByte(v16, 0, lpszDestAddress, cchWideChar, &v23[v25 + 160], cbMultiByte, 0, 0);
              }
              else
              {
                *((_DWORD *)v21 + 39) = 0;
              }
              if ( lpCallParams )
              {
                *((_BYTE *)v21 + 160) = 0;
                memcpy_0((char *)v21 + 164, lpCallParams, lpCallParams->dwTotalSize);
                dwOrigAddressSize = lpCallParams->dwOrigAddressSize;
                if ( dwOrigAddressSize )
                {
                  WideCharToMultiByte(
                    0,
                    0,
                    (LPCWCH)((char *)lpCallParams + lpCallParams->dwOrigAddressOffset),
                    dwOrigAddressSize >> 1,
                    &v23[lpCallParams->dwOrigAddressOffset + 44],
                    dwOrigAddressSize,
                    0,
                    0);
                  *((_DWORD *)v21 + 53) >>= 1;
                }
              }
              else
              {
                *((_BYTE *)v21 + 160) = 1;
              }
              v21[12] = v22;
              v21[5] = TSPI_lineMakeCall_postProcess;
              *lphdCall = v22;
              Lock = AsyncDriverRequest(0x8FFF23C8, v21);
              goto LABEL_30;
            }
            TspLog(1, "lineMakeCall: failed to reacquire read lock for obj(%p)", hdLine);
            FreeRequest(v27);
            CloseObjHandle(v29[0]);
          }
          return Lock;
        }
        FreeCallObj(v12);
LABEL_30:
        ReleaseObjReadLock(hdLine);
        return Lock;
      }
      v16 = 0;
    }
    cbMultiByte = v18;
    goto LABEL_11;
  }
  return result;
}

```

## disassembly

```asm
0x1800063b0  mov     [rsp-40h+arg_18], r9
0x1800063b5  push    rbp
0x1800063b6  push    rbx
0x1800063b7  push    rsi
0x1800063b8  push    rdi
0x1800063b9  push    r12
0x1800063bb  push    r13
0x1800063bd  push    r14
0x1800063bf  push    r15
0x1800063c1  mov     rbp, rsp
0x1800063c4  sub     rsp, 68h
0x1800063c8  xor     esi, esi
0x1800063ca  mov     [rsp+68h+lpMultiByteStr], rdx
0x1800063cf  mov     rbx, r8
0x1800063d2  mov     [rbp+var_18], rsi
0x1800063d6  mov     r8d, cs:dword_18000E2A0
0x1800063dd  mov     r12, rdx
0x1800063e0  mov     r13d, ecx
0x1800063e3  mov     [rbp+var_10], rsi
0x1800063e7  mov     r9d, ecx
0x1800063ea  mov     [rbp+var_20], rsi
0x1800063ee  lea     r14d, [rsi+1]
0x1800063f2  add     r8d, r14d
0x1800063f5  lea     rdx, aLinemakecallDR; "lineMakeCall(%d): reqID(%x), line(%p)"
0x1800063fc  lea     ecx, [rsi+8]
0x1800063ff  mov     cs:dword_18000E2A0, r8d
0x180006406  call    TspLog
0x18000640b  lea     rdx, [rbp+var_18]
0x18000640f  mov     rcx, r12
0x180006412  call    GetLineObjWithReadLock
0x180006417  test    eax, eax
0x180006419  jnz     loc_1800066BD
0x18000641f  call    AllocCallObj
0x180006424  mov     rdi, rax
0x180006427  test    rax, rax
0x18000642a  jnz     short loc_180006445
0x18000642c  lea     rdx, aLinemakecallFa_0; "lineMakeCall: failed to create call obj"
0x180006433  mov     ecx, r14d
0x180006436  call    TspLog
0x18000643b  mov     ebx, 80000044h
0x180006440  jmp     loc_1800066B3
0x180006445  mov     rcx, [rbp+var_18]
0x180006449  mov     dword ptr [rax], 4F43414Ch
0x18000644f  mov     eax, [rcx+4]
0x180006452  mov     [rdi+40h], r14d
0x180006456  mov     r14d, 0FDE9h
0x18000645c  mov     [rdi+4], eax
0x18000645f  mov     [rdi+8], rbx
0x180006463  mov     [rdi+20h], r12
0x180006467  mov     r15d, [rcx+30h]
0x18000646b  cmp     r15d, 0Ch
0x18000646f  cmovnz  r14d, esi
0x180006473  mov     rsi, [rbp+lpszDestAddress]
0x180006477  test    rsi, rsi
0x18000647a  jz      short loc_1800064D6
0x18000647c  mov     rcx, rsi; lpString
0x18000647f  call    cs:__imp_lstrlenW
0x180006486  nop     dword ptr [rax+rax+00h]
0x18000648b  lea     ebx, [rax+1]
0x18000648e  mov     [rbp+cchWideChar], ebx
0x180006491  cmp     r15d, 0Ch
0x180006495  jnz     short loc_1800064CD
0x180006497  xor     eax, eax
0x180006499  mov     r9d, ebx; cchWideChar
0x18000649c  mov     [rsp+68h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800064a1  mov     r8, rsi; lpWideCharStr
0x1800064a4  mov     [rsp+68h+lpDefaultChar], rax; lpDefaultChar
0x1800064a9  xor     edx, edx; dwFlags
0x1800064ab  mov     [rsp+68h+cbMultiByte], eax; cbMultiByte
0x1800064af  mov     ecx, r14d; CodePage
0x1800064b2  mov     [rsp+68h+lpMultiByteStr], rax; lpMultiByteStr
0x1800064b7  call    cs:__imp_WideCharToMultiByte
0x1800064be  nop     dword ptr [rax+rax+00h]
0x1800064c3  mov     r15d, eax
0x1800064c6  test    eax, eax
0x1800064c8  jnz     short loc_1800064D0
0x1800064ca  xor     r14d, r14d
0x1800064cd  mov     r15d, ebx
0x1800064d0  mov     rcx, [rbp+var_18]
0x1800064d4  jmp     short loc_1800064DD
0x1800064d6  xor     r15d, r15d
0x1800064d9  mov     [rbp+cchWideChar], r15d
0x1800064dd  mov     rsi, [rbp+lpCallParams]
0x1800064e1  test    rsi, rsi
0x1800064e4  jz      short loc_1800064ED
0x1800064e6  mov     eax, [rsi]
0x1800064e8  sub     eax, 70h ; 'p'
0x1800064eb  jmp     short loc_1800064EF
0x1800064ed  xor     eax, eax
0x1800064ef  mov     edx, [rcx+4]
0x1800064f2  lea     r9d, [rax+0A0h]
0x1800064f9  mov     [rbp+var_28], eax
0x1800064fc  add     r9d, r15d
0x1800064ff  lea     rax, [rbp+var_20]
0x180006503  mov     r8d, r13d
0x180006506  mov     ecx, 7030115h
0x18000650b  mov     [rsp+68h+lpMultiByteStr], rax
0x180006510  call    PrepareAsyncRequest
0x180006515  mov     ebx, eax
0x180006517  test    eax, eax
0x180006519  jz      short loc_180006528
0x18000651b  mov     rcx, rdi
0x18000651e  call    FreeCallObj
0x180006523  jmp     loc_1800066B3
0x180006528  mov     rcx, r12
0x18000652b  call    ReleaseObjReadLock
0x180006530  lea     r8, [rbp+var_10]
0x180006534  mov     rcx, rdi
0x180006537  lea     rdx, FreeCallObj
0x18000653e  call    OpenObjHandle
0x180006543  mov     ebx, eax
0x180006545  test    eax, eax
0x180006547  jz      short loc_180006573
0x180006549  mov     r8, rdi
0x18000654c  lea     rdx, aLinemakecallFa; "lineMakeCall: failed to map obj(%p) to "...
0x180006553  mov     ecx, 1
0x180006558  call    TspLog
0x18000655d  mov     rcx, [rbp+var_20]; void *
0x180006561  call    FreeRequest
0x180006566  mov     rcx, rdi
0x180006569  call    FreeCallObj
0x18000656e  jmp     loc_1800066BB
0x180006573  mov     rcx, r12
0x180006576  call    AcquireObjReadLock
0x18000657b  mov     ebx, eax
0x18000657d  test    eax, eax
0x18000657f  jz      short loc_1800065AC
0x180006581  mov     r8, r12
0x180006584  lea     rdx, aLinemakecallFa_1; "lineMakeCall: failed to reacquire read "...
0x18000658b  mov     ecx, 1
0x180006590  call    TspLog
0x180006595  mov     rcx, [rbp+var_20]; void *
0x180006599  call    FreeRequest
0x18000659e  mov     rcx, [rbp+var_10]
0x1800065a2  call    CloseObjHandle
0x1800065a7  jmp     loc_1800066BB
0x1800065ac  mov     rax, [rbp+var_10]
0x1800065b0  mov     r13, [rbp+var_20]
0x1800065b4  mov     r8, [rbp+lpszDestAddress]; lpWideCharStr
0x1800065b8  mov     [rdi+10h], rax
0x1800065bc  mov     rax, [rbp+var_18]
0x1800065c0  mov     rdi, [rbp+var_10]
0x1800065c4  lea     rbx, [r13+78h]
0x1800065c8  mov     rax, [rax+10h]
0x1800065cc  mov     [rbx+8], rax
0x1800065d0  mov     [rbx+10h], rdi
0x1800065d4  mov     [rbx+20h], r15d
0x1800065d8  test    r8, r8
0x1800065db  jz      short loc_180006620
0x1800065dd  mov     eax, [rbp+var_28]
0x1800065e0  mov     ecx, r14d; CodePage
0x1800065e3  mov     r9d, [rbp+cchWideChar]; cchWideChar
0x1800065e7  add     eax, 0A0h
0x1800065ec  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800065f5  mov     edx, eax
0x1800065f7  add     rdx, rbx
0x1800065fa  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x180006603  mov     [rsp+68h+cbMultiByte], r15d; cbMultiByte
0x180006608  mov     [rsp+68h+lpMultiByteStr], rdx; lpMultiByteStr
0x18000660d  xor     edx, edx; dwFlags
0x18000660f  mov     [rbx+24h], eax
0x180006612  call    cs:__imp_WideCharToMultiByte
0x180006619  nop     dword ptr [rax+rax+00h]
0x18000661e  jmp     short loc_180006627
0x180006620  mov     dword ptr [rbx+24h], 0
0x180006627  test    rsi, rsi
0x18000662a  jz      short loc_18000668A
0x18000662c  mov     byte ptr [rbx+28h], 0
0x180006630  lea     rcx, [rbx+2Ch]; void *
0x180006634  mov     r8d, [rsi]; Size
0x180006637  mov     rdx, rsi; Src
0x18000663a  call    memcpy_0
0x18000663f  mov     edx, [rsi+30h]
0x180006642  test    edx, edx
0x180006644  jz      short loc_18000668E
0x180006646  mov     eax, [rsi+34h]
0x180006649  mov     r9d, edx
0x18000664c  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180006655  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x18000665e  mov     [rsp+68h+cbMultiByte], edx; cbMultiByte
0x180006662  xor     edx, edx; dwFlags
0x180006664  lea     rcx, [rax+2Ch]
0x180006668  shr     r9d, 1; cchWideChar
0x18000666b  add     rcx, rbx
0x18000666e  lea     r8, [rax+rsi]; lpWideCharStr
0x180006672  mov     [rsp+68h+lpMultiByteStr], rcx; lpMultiByteStr
0x180006677  xor     ecx, ecx; CodePage
0x180006679  call    cs:__imp_WideCharToMultiByte
0x180006680  nop     dword ptr [rax+rax+00h]
0x180006685  shr     dword ptr [rbx+5Ch], 1
0x180006688  jmp     short loc_18000668E
0x18000668a  mov     byte ptr [rbx+28h], 1
0x18000668e  mov     [r13+60h], rdi
0x180006692  lea     rax, TSPI_lineMakeCall_postProcess
0x180006699  mov     [r13+28h], rax
0x18000669d  mov     rdx, r13; void *
0x1800066a0  mov     rax, [rbp+arg_18]
0x1800066a4  mov     ecx, 8FFF23C8h; dwIoControlCode
0x1800066a9  mov     [rax], rdi
0x1800066ac  call    AsyncDriverRequest
0x1800066b1  mov     ebx, eax
0x1800066b3  mov     rcx, r12
0x1800066b6  call    ReleaseObjReadLock
0x1800066bb  mov     eax, ebx
0x1800066bd  add     rsp, 68h
0x1800066c1  pop     r15
0x1800066c3  pop     r14
0x1800066c5  pop     r13
0x1800066c7  pop     r12
0x1800066c9  pop     rdi
0x1800066ca  pop     rsi
0x1800066cb  pop     rbx
0x1800066cc  pop     rbp
0x1800066cd  retn
```
