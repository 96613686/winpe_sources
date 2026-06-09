# RasLineCloseCall

- ea: `0x180085e4c`
- end: `0x180086253`
- name: `RasLineCloseCall`
- size: `1031`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: ``

## callers

- `0x1800263c4`
- `0x180027da0`
- `0x180028570`

## callees

- `0x180071cec`
- `0x18008490c`
- `0x180085e4c`
- `0x1800884f8`
- `0x180088b1c`
- `0x180089134`
- `0x180089450`
- `0x1800895e4`
- `0x180089924`
- `0x180089a9c`
- `0x18008a408`
- `0x18008a51c`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180086212`
- `KERNEL32!GetProcessHeap` at `0x180086212`
- `KERNEL32!HeapFree` at `0x180086220`
- `KERNEL32!HeapFree` at `0x180086220`
- `rtutils!TracePrintfA` at `0x180085f32`
- `rtutils!TracePrintfA` at `0x180086127`
- `rtutils!TracePrintfA` at `0x1800861b6`
- `rtutils!TracePrintfA` at `0x180085f32`
- `rtutils!TracePrintfA` at `0x180086127`
- `rtutils!TracePrintfA` at `0x1800861b6`

## string_xrefs

- `0x180085f80`: `RasLineCloseCall: GetCallObjWithReadLock failed with error (0x%x)`
- `0x180085f65`: `RasLineCloseCall: GetCallObjWithReadLock failed with error (0x%x)`
- `0x180086026`: `RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)`
- `0x18008600b`: `RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)`
- `0x180086077`: `RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)`
- `0x18008605c`: `RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineCloseCall(unsigned int a1)
{
  unsigned int NDProxyHandle; // eax
  unsigned int v3; // ebx
  const wchar_t *v4; // rdx
  _DWORD *v5; // rdi
  int v6; // r12d
  unsigned int v7; // eax
  _QWORD *v8; // r14
  __int64 v9; // rax
  void *v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  HANDLE ProcessHeap; // rax
  unsigned int v16; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD *v17; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[2044]; // [rsp+54h] [rbp-ACh] BYREF

  lpMem = 0;
  v19 = 0;
  v17 = 0;
  v20 = 0;
  v16 = 0;
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  NDProxyHandle = GetLineHandleFromCallHandle(a1, &v16);
  v3 = NDProxyHandle;
  if ( NDProxyHandle )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        v4 = L"RasLineCloseCall: GetLineHandleFromCallHandle failed with error (0x%x)";
LABEL_5:
        LOWORD(v21) = 0;
        FormatRRASErrorString(&v21, v4, NDProxyHandle);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v21);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineCloseCall: GetLineHandleFromCallHandle failed with error (0x%x)", NDProxyHandle);
    }
  }
  else
  {
    NDProxyHandle = GetCallObjWithReadLock(a1, &v17);
    v3 = NDProxyHandle;
    if ( NDProxyHandle )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800C9BE0 )
          return v3;
        v4 = L"RasLineCloseCall: GetCallObjWithReadLock failed with error (0x%x)";
        goto LABEL_5;
      }
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineCloseCall: GetCallObjWithReadLock failed with error (0x%x)", NDProxyHandle);
    }
    else
    {
      v5 = v17;
      v6 = *v17;
      NDProxyHandle = GetNDProxyHandle(v17, &v19);
      v3 = NDProxyHandle;
      if ( NDProxyHandle )
      {
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( !(_QWORD)xmmword_1800C9BE0 )
            return v3;
          v4 = L"RasLineCloseCall: GetNDProxyHandle failed with error (0x%x)";
          goto LABEL_5;
        }
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineCloseCall: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
      }
      else
      {
        ReleaseObjReadLock(a1);
        NDProxyHandle = AcquireObjWriteLock(a1);
        v3 = NDProxyHandle;
        if ( NDProxyHandle )
        {
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( !(_QWORD)xmmword_1800C9BE0 )
              return v3;
            v4 = L"RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)";
            goto LABEL_5;
          }
          if ( dwTraceId != -1 )
            TracePrintfA(dwTraceId, "RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)", NDProxyHandle);
        }
        else
        {
          NDProxyHandle = GetLineObjWithWriteLock(v16, &v20);
          v3 = NDProxyHandle;
          if ( NDProxyHandle )
          {
            if ( gIsndpspEtwTracingAvailable )
            {
              if ( !(_QWORD)xmmword_1800C9BE0 )
                return v3;
              v4 = L"RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)";
              goto LABEL_5;
            }
            if ( dwTraceId != -1 )
              TracePrintfA(dwTraceId, "RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)", NDProxyHandle);
          }
          else
          {
            v7 = PrepareSyncRequest(117637380, (unsigned int)v5[1], 16, &lpMem);
            v8 = lpMem;
            v3 = v7;
            if ( v7 )
            {
              ReleaseObjWriteLock(a1);
              ReleaseObjWriteLock(v16);
              if ( gIsndpspEtwTracingAvailable )
              {
                if ( (_QWORD)xmmword_1800C9BE0 )
                {
                  LOWORD(v21) = 0;
                  FormatRRASErrorString(&v21, L"RasLineCloseCall: PrepareSyncRequest failed with error (0x%x)", v3);
                  ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                    gNdpspEtwContext,
                    xmmword_1800C9BE0,
                    &v21);
                }
              }
              else if ( dwTraceId != -1 )
              {
                TracePrintfA(dwTraceId, "RasLineCloseCall: PrepareSyncRequest failed with error (0x%x)", v3);
              }
            }
            else
            {
              v9 = v19;
              v10 = lpMem;
              *v5 = 1482184792;
              v8[7] = v9;
              v11 = SyncDriverRequest(0x8FFF23CC, v10);
              v3 = v11;
              if ( v11 )
              {
                if ( gIsndpspEtwTracingAvailable )
                {
                  if ( (_QWORD)xmmword_1800C9BE0 )
                  {
                    LOWORD(v21) = 0;
                    FormatRRASErrorString(
                      &v21,
                      L"RasLineClose: SyncDriverRequest(OID_TAPI_CLOSE_CALL) failed with error (0x%x)",
                      v11);
                    ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                      gNdpspEtwContext,
                      xmmword_1800C9BE0,
                      &v21);
                  }
                }
                else if ( dwTraceId != -1 )
                {
                  TracePrintfA(
                    dwTraceId,
                    "RasLineClose: SyncDriverRequest(OID_TAPI_CLOSE_CALL) failed with error (0x%x)",
                    v11);
                }
              }
              if ( v6 == 1229144396 )
              {
                v12 = *((_QWORD *)v5 + 7);
                if ( v12 )
                  *(_QWORD *)(v12 + 48) = *((_QWORD *)v5 + 6);
                v13 = *((_QWORD *)v5 + 6);
                if ( v13 )
                  *(_QWORD *)(v13 + 56) = *((_QWORD *)v5 + 7);
                else
                  *(_QWORD *)(v20 + 24) = *((_QWORD *)v5 + 7);
              }
              ReleaseObjWriteLock(a1);
              ReleaseObjWriteLock(v16);
              CloseObjHandle(a1);
            }
            if ( v8 )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v8);
            }
          }
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180085e4c  mov     [rsp-8+arg_8], rbx
0x180085e51  mov     [rsp-8+arg_10], rsi
0x180085e56  push    rbp
0x180085e57  push    rdi
0x180085e58  push    r12
0x180085e5a  push    r13
0x180085e5c  push    r14
0x180085e5e  lea     rbp, [rsp-760h]
0x180085e66  sub     rsp, 860h
0x180085e6d  mov     rax, cs:__security_cookie
0x180085e74  xor     rax, rsp
0x180085e77  mov     [rbp+780h+var_30], rax
0x180085e7e  xor     r13d, r13d
0x180085e81  mov     esi, ecx
0x180085e83  lea     rcx, [rsp+880h+var_82C]; void *
0x180085e88  mov     [rsp+880h+lpMem], r13
0x180085e8d  xor     edx, edx; Val
0x180085e8f  mov     [rsp+880h+var_848], r13
0x180085e94  mov     r8d, 7FCh; Size
0x180085e9a  mov     [rsp+880h+var_858], r13
0x180085e9f  mov     [rsp+880h+var_840], r13
0x180085ea4  mov     [rsp+880h+var_860], r13d
0x180085ea9  mov     [rsp+880h+var_830], r13d
0x180085eae  call    memset_0
0x180085eb3  lea     rdx, [rsp+880h+var_860]
0x180085eb8  mov     ecx, esi
0x180085eba  call    GetLineHandleFromCallHandle
0x180085ebf  mov     ebx, eax
0x180085ec1  test    eax, eax
0x180085ec3  jz      short loc_180085F3D
0x180085ec5  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180085ecc  jz      short loc_180085F19
0x180085ece  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180085ed5  jz      loc_180086226
0x180085edb  lea     rdx, aRaslinecloseca_7; "RasLineCloseCall: GetLineHandleFromCall"...
0x180085ee2  mov     r8d, eax
0x180085ee5  mov     word ptr [rsp+880h+var_830], r13w
0x180085eeb  lea     rcx, [rsp+880h+var_830]
0x180085ef0  call    FormatRRASErrorString
0x180085ef5  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180085efc  lea     r8, [rsp+880h+var_830]
0x180085f01  mov     rcx, cs:gNdpspEtwContext
0x180085f08  mov     rax, cs:gNdpspTemplateFunc
0x180085f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085f14  jmp     loc_180086226
0x180085f19  mov     ecx, cs:dwTraceId; dwTraceID
0x180085f1f  cmp     ecx, 0FFFFFFFFh
0x180085f22  jz      loc_180086226
0x180085f28  lea     rdx, aRaslinecloseca_3; "RasLineCloseCall: GetLineHandleFromCall"...
0x180085f2f  mov     r8d, eax
0x180085f32  call    cs:__imp_TracePrintfA
0x180085f38  jmp     loc_180086226
0x180085f3d  lea     rdx, [rsp+880h+var_858]
0x180085f42  mov     ecx, esi
0x180085f44  call    GetCallObjWithReadLock
0x180085f49  mov     ebx, eax
0x180085f4b  test    eax, eax
0x180085f4d  jz      short loc_180085F89
0x180085f4f  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180085f56  jz      short loc_180085F71
0x180085f58  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180085f5f  jz      loc_180086226
0x180085f65  lea     rdx, aRaslinecloseca_6; "RasLineCloseCall: GetCallObjWithReadLoc"...
0x180085f6c  jmp     loc_180085EE2
0x180085f71  mov     ecx, cs:dwTraceId
0x180085f77  cmp     ecx, 0FFFFFFFFh
0x180085f7a  jz      loc_180086226
0x180085f80  lea     rdx, aRaslinecloseca; "RasLineCloseCall: GetCallObjWithReadLoc"...
0x180085f87  jmp     short loc_180085F2F
0x180085f89  mov     rdi, [rsp+880h+var_858]
0x180085f8e  lea     rdx, [rsp+880h+var_848]
0x180085f93  mov     rcx, rdi
0x180085f96  mov     r12d, [rdi]
0x180085f99  call    GetNDProxyHandle
0x180085f9e  mov     ebx, eax
0x180085fa0  test    eax, eax
0x180085fa2  jz      short loc_180085FE1
0x180085fa4  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180085fab  jz      short loc_180085FC6
0x180085fad  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180085fb4  jz      loc_180086226
0x180085fba  lea     rdx, aRaslinecloseca_2; "RasLineCloseCall: GetNDProxyHandle fail"...
0x180085fc1  jmp     loc_180085EE2
0x180085fc6  mov     ecx, cs:dwTraceId
0x180085fcc  cmp     ecx, 0FFFFFFFFh
0x180085fcf  jz      loc_180086226
0x180085fd5  lea     rdx, aRaslinecloseca_4; "RasLineCloseCall: GetNDProxyHandle fail"...
0x180085fdc  jmp     loc_180085F2F
0x180085fe1  mov     ecx, esi
0x180085fe3  call    ReleaseObjReadLock
0x180085fe8  mov     ecx, esi
0x180085fea  call    AcquireObjWriteLock
0x180085fef  mov     ebx, eax
0x180085ff1  test    eax, eax
0x180085ff3  jz      short loc_180086032
0x180085ff5  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180085ffc  jz      short loc_180086017
0x180085ffe  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180086005  jz      loc_180086226
0x18008600b  lea     rdx, aRaslinecloseca_8; "RasLineCloseCall: AcquireObjWriteLock f"...
0x180086012  jmp     loc_180085EE2
0x180086017  mov     ecx, cs:dwTraceId
0x18008601d  cmp     ecx, 0FFFFFFFFh
0x180086020  jz      loc_180086226
0x180086026  lea     rdx, aRaslinecloseca_1; "RasLineCloseCall: AcquireObjWriteLock f"...
0x18008602d  jmp     loc_180085F2F
0x180086032  mov     ecx, [rsp+880h+var_860]
0x180086036  lea     rdx, [rsp+880h+var_840]
0x18008603b  call    GetLineObjWithWriteLock
0x180086040  mov     ebx, eax
0x180086042  test    eax, eax
0x180086044  jz      short loc_180086083
0x180086046  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008604d  jz      short loc_180086068
0x18008604f  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180086056  jz      loc_180086226
0x18008605c  lea     rdx, aRaslinecloseGe_0; "RasLineClose: GetLineObjWithWriteLock f"...
0x180086063  jmp     loc_180085EE2
0x180086068  mov     ecx, cs:dwTraceId
0x18008606e  cmp     ecx, 0FFFFFFFFh
0x180086071  jz      loc_180086226
0x180086077  lea     rdx, aRaslinecloseGe; "RasLineClose: GetLineObjWithWriteLock f"...
0x18008607e  jmp     loc_180085F2F
0x180086083  mov     edx, [rdi+4]
0x180086086  lea     r9, [rsp+880h+lpMem]
0x18008608b  mov     r8d, 10h
0x180086091  mov     ecx, 7030104h
0x180086096  call    PrepareSyncRequest
0x18008609b  mov     r14, [rsp+880h+lpMem]
0x1800860a0  mov     ebx, eax
0x1800860a2  test    eax, eax
0x1800860a4  jz      loc_180086132
0x1800860aa  mov     ecx, esi
0x1800860ac  call    ReleaseObjWriteLock
0x1800860b1  mov     ecx, [rsp+880h+var_860]
0x1800860b5  call    ReleaseObjWriteLock
0x1800860ba  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x1800860c1  jz      short loc_18008610E
0x1800860c3  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x1800860ca  jz      loc_18008620D
0x1800860d0  mov     r8d, ebx
0x1800860d3  mov     word ptr [rsp+880h+var_830], r13w
0x1800860d9  lea     rdx, aRaslinecloseca_0; "RasLineCloseCall: PrepareSyncRequest fa"...
0x1800860e0  lea     rcx, [rsp+880h+var_830]
0x1800860e5  call    FormatRRASErrorString
0x1800860ea  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x1800860f1  lea     r8, [rsp+880h+var_830]
0x1800860f6  mov     rcx, cs:gNdpspEtwContext
0x1800860fd  mov     rax, cs:gNdpspTemplateFunc
0x180086104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086109  jmp     loc_18008620D
0x18008610e  mov     ecx, cs:dwTraceId; dwTraceID
0x180086114  cmp     ecx, 0FFFFFFFFh
0x180086117  jz      loc_18008620D
0x18008611d  mov     r8d, ebx
0x180086120  lea     rdx, aRaslinecloseca_5; "RasLineCloseCall: PrepareSyncRequest fa"...
0x180086127  call    cs:__imp_TracePrintfA
0x18008612d  jmp     loc_18008620D
0x180086132  mov     rax, [rsp+880h+var_848]
0x180086137  mov     rdx, r14; lpInBuffer
0x18008613a  mov     dword ptr [rdi], 58585858h
0x180086140  mov     ecx, 8FFF23CCh; dwIoControlCode
0x180086145  mov     [r14+38h], rax
0x180086149  call    SyncDriverRequest
0x18008614e  mov     ebx, eax
0x180086150  test    eax, eax
0x180086152  jz      short loc_1800861BC
0x180086154  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008615b  jz      short loc_1800861A1
0x18008615d  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180086164  jz      short loc_1800861BC
0x180086166  mov     r8d, eax
0x180086169  mov     word ptr [rsp+880h+var_830], r13w
0x18008616f  lea     rdx, aRaslinecloseSy_1; "RasLineClose: SyncDriverRequest(OID_TAP"...
0x180086176  lea     rcx, [rsp+880h+var_830]
0x18008617b  call    FormatRRASErrorString
0x180086180  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180086187  lea     r8, [rsp+880h+var_830]
0x18008618c  mov     rcx, cs:gNdpspEtwContext
0x180086193  mov     rax, cs:gNdpspTemplateFunc
0x18008619a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008619f  jmp     short loc_1800861BC
0x1800861a1  mov     ecx, cs:dwTraceId; dwTraceID
0x1800861a7  cmp     ecx, 0FFFFFFFFh
0x1800861aa  jz      short loc_1800861BC
0x1800861ac  mov     r8d, eax
0x1800861af  lea     rdx, aRaslinecloseSy_2; "RasLineClose: SyncDriverRequest(OID_TAP"...
0x1800861b6  call    cs:__imp_TracePrintfA
0x1800861bc  cmp     r12d, 4943414Ch
0x1800861c3  jnz     short loc_1800861F6
0x1800861c5  mov     rcx, [rdi+38h]
0x1800861c9  test    rcx, rcx
0x1800861cc  jz      short loc_1800861D6
0x1800861ce  mov     rax, [rdi+30h]
0x1800861d2  mov     [rcx+30h], rax
0x1800861d6  mov     rcx, [rdi+30h]
0x1800861da  test    rcx, rcx
0x1800861dd  jz      short loc_1800861E9
0x1800861df  mov     rax, [rdi+38h]
0x1800861e3  mov     [rcx+38h], rax
0x1800861e7  jmp     short loc_1800861F6
0x1800861e9  mov     rax, [rsp+880h+var_840]
0x1800861ee  mov     rcx, [rdi+38h]
0x1800861f2  mov     [rax+18h], rcx
0x1800861f6  mov     ecx, esi
0x1800861f8  call    ReleaseObjWriteLock
0x1800861fd  mov     ecx, [rsp+880h+var_860]
0x180086201  call    ReleaseObjWriteLock
0x180086206  mov     ecx, esi
0x180086208  call    CloseObjHandle
0x18008620d  test    r14, r14
0x180086210  jz      short loc_180086226
0x180086212  call    cs:__imp_GetProcessHeap
0x180086218  mov     r8, r14; lpMem
0x18008621b  xor     edx, edx; dwFlags
0x18008621d  mov     rcx, rax; hHeap
0x180086220  call    cs:__imp_HeapFree
0x180086226  mov     eax, ebx
0x180086228  mov     rcx, [rbp+780h+var_30]
0x18008622f  xor     rcx, rsp; StackCookie
0x180086232  call    __security_check_cookie
0x180086237  lea     r11, [rsp+880h+var_20]
0x18008623f  mov     rbx, [r11+38h]
0x180086243  mov     rsi, [r11+40h]
0x180086247  mov     rsp, r11
0x18008624a  pop     r14
0x18008624c  pop     r13
0x18008624e  pop     r12
0x180086250  pop     rdi
0x180086251  pop     rbp
0x180086252  retn
```
