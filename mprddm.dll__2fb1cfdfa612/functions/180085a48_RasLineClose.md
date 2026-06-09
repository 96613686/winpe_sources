# RasLineClose

- ea: `0x180085a48`
- end: `0x180085e44`
- name: `RasLineClose`
- size: `1020`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001f8e0`
- `0x180026e38`

## callees

- `0x180071cec`
- `0x18008490c`
- `0x180085a48`
- `0x1800884f8`
- `0x180089450`
- `0x180089a9c`
- `0x18008a51c`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180085df8`
- `KERNEL32!ReleaseMutex` at `0x180085df8`
- `KERNEL32!GetProcessHeap` at `0x180085dce`
- `KERNEL32!GetProcessHeap` at `0x180085e03`
- `KERNEL32!GetProcessHeap` at `0x180085dce`
- `KERNEL32!GetProcessHeap` at `0x180085e03`
- `KERNEL32!WaitForSingleObject` at `0x180085aad`
- `KERNEL32!WaitForSingleObject` at `0x180085aad`
- `KERNEL32!HeapFree` at `0x180085ddc`
- `KERNEL32!HeapFree` at `0x180085e11`
- `KERNEL32!HeapFree` at `0x180085ddc`
- `KERNEL32!HeapFree` at `0x180085e11`
- `rtutils!TracePrintfA` at `0x180085b25`
- `rtutils!TracePrintfA` at `0x180085baf`
- `rtutils!TracePrintfA` at `0x180085c4b`
- `rtutils!TracePrintfA` at `0x180085ce5`
- `rtutils!TracePrintfA` at `0x180085d80`
- `rtutils!TracePrintfA` at `0x180085b25`
- `rtutils!TracePrintfA` at `0x180085baf`
- `rtutils!TracePrintfA` at `0x180085c4b`
- `rtutils!TracePrintfA` at `0x180085ce5`
- `rtutils!TracePrintfA` at `0x180085d80`

## string_xrefs

- `0x180085ba8`: `RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)`
- `0x180085b5a`: `RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineClose(unsigned int a1)
{
  _QWORD *v2; // rsi
  DWORD v3; // eax
  DWORD v4; // ebx
  DWORD v5; // eax
  unsigned int *v6; // r15
  _DWORD *v7; // rdi
  _DWORD *v8; // rax
  unsigned int v9; // r12d
  unsigned int v10; // eax
  DWORD v11; // eax
  _QWORD *v12; // rcx
  _DWORD *v13; // rdi
  LPVOID v14; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  LPVOID lpInBuffer; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int *v19; // [rsp+28h] [rbp-D8h] BYREF
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  char v21[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v2 = 0;
  lpInBuffer = 0;
  v19 = 0;
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v3 = WaitForSingleObject(g_hRasOpenLinesMutex, 0xFFFFFFFF);
  v4 = v3;
  if ( v3 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"RasLineClose: WaitForSingleObject failed with error 0x%x", v3);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v20);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineClose: WaitForSingleObject failed with error 0x%x", v3);
    }
  }
  else
  {
    v5 = GetLineObjWithWriteLock(a1, &v19);
    v4 = v5;
    if ( v5 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v20) = 0;
          FormatRRASErrorString(&v20, L"RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)", v5);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v20);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)", v5);
      }
    }
    else
    {
      v6 = v19;
      v7 = 0;
      v8 = g_pRasOpenLines;
      v9 = v19[1];
      while ( v8 )
      {
        if ( v9 == v8[3] )
        {
          v7 = v8;
          break;
        }
        v8 = *(_DWORD **)v8;
      }
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v20) = 0;
          FormatRRASErrorString(
            &v20,
            L"RasLineClose: RasTapi line handle (%p). Reference count (0x%x)",
            a1,
            (unsigned int)v7[5]);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v20);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(
          dwTraceId,
          "RasLineClose: RasTapi line handle (%p). Reference count (0x%x)",
          (const void *)a1,
          v7[5]);
      }
      v10 = v7[5];
      if ( v10 > 1 )
      {
        v7[5] = v10 - 1;
        ReleaseObjWriteLock(a1);
      }
      else
      {
        v4 = PrepareSyncRequest(117637379, v9, 16, &lpInBuffer);
        if ( v4 )
        {
          ReleaseObjWriteLock(a1);
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( (_QWORD)xmmword_1800C9BE0 )
            {
              LOWORD(v20) = 0;
              FormatRRASErrorString(&v20, L"RasLineClose: PrepareSyncRequest failed with error (0x%x)", v4);
              ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                xmmword_1800C9BE0,
                &v20);
            }
          }
          else if ( dwTraceId != -1 )
          {
            TracePrintfA(dwTraceId, "RasLineClose: PrepareSyncRequest failed with error (0x%x)", v4);
          }
          v2 = lpInBuffer;
        }
        else
        {
          v2 = lpInBuffer;
          *v6 = 1482184792;
          v2[7] = *((_QWORD *)v6 + 2);
          v11 = SyncDriverRequest(0x8FFF23CC, v2);
          v4 = v11;
          if ( v11 )
          {
            if ( gIsndpspEtwTracingAvailable )
            {
              if ( (_QWORD)xmmword_1800C9BE0 )
              {
                LOWORD(v20) = 0;
                FormatRRASErrorString(
                  &v20,
                  L"RasLineClose: SyncDriverRequest(OID_TAPI_CLOSE) failed with error (0x%x)",
                  v11);
                ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                  gNdpspEtwContext,
                  xmmword_1800C9BE0,
                  &v20);
              }
            }
            else if ( dwTraceId != -1 )
            {
              TracePrintfA(dwTraceId, "RasLineClose: SyncDriverRequest(OID_TAPI_CLOSE) failed with error (0x%x)", v11);
            }
          }
          ReleaseObjWriteLock(a1);
          CloseObjHandle(a1);
          --v7[5];
          v12 = 0;
          v13 = g_pRasOpenLines;
          if ( g_pRasOpenLines )
          {
            while ( 1 )
            {
              v14 = *(LPVOID *)v13;
              if ( v9 == v13[3] )
                break;
              v12 = v13;
              v13 = *(_DWORD **)v13;
              if ( !v14 )
                goto LABEL_47;
            }
            if ( v12 )
              *v12 = v14;
            else
              g_pRasOpenLines = *(LPVOID *)v13;
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v13);
          }
        }
      }
    }
LABEL_47:
    ReleaseMutex(g_hRasOpenLinesMutex);
    if ( v2 )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v2);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180085a48  mov     [rsp-8+arg_8], rbx
0x180085a4d  mov     [rsp-8+arg_10], rsi
0x180085a52  push    rbp
0x180085a53  push    rdi
0x180085a54  push    r12
0x180085a56  push    r14
0x180085a58  push    r15
0x180085a5a  lea     rbp, [rsp-740h]
0x180085a62  sub     rsp, 840h
0x180085a69  mov     rax, cs:__security_cookie
0x180085a70  xor     rax, rsp
0x180085a73  mov     [rbp+760h+var_30], rax
0x180085a7a  mov     r14d, ecx
0x180085a7d  xor     esi, esi
0x180085a7f  xor     eax, eax
0x180085a81  mov     [rsp+860h+lpInBuffer], rsi
0x180085a86  lea     rcx, [rsp+860h+var_82C]; void *
0x180085a8b  mov     [rsp+860h+var_838], rsi
0x180085a90  xor     edx, edx; Val
0x180085a92  mov     [rsp+860h+var_830], eax
0x180085a96  mov     r8d, 7FCh; Size
0x180085a9c  call    memset_0
0x180085aa1  mov     rcx, cs:g_hRasOpenLinesMutex; hHandle
0x180085aa8  or      edi, 0FFFFFFFFh
0x180085aab  mov     edx, edi; dwMilliseconds
0x180085aad  call    cs:__imp_WaitForSingleObject
0x180085ab3  mov     ebx, eax
0x180085ab5  test    eax, eax
0x180085ab7  jz      short loc_180085B30
0x180085ab9  cmp     cs:gIsndpspEtwTracingAvailable, esi
0x180085abf  jz      short loc_180085B0D
0x180085ac1  cmp     qword ptr cs:xmmword_1800C9BE0, rsi
0x180085ac8  jz      loc_180085E17
0x180085ace  xor     ecx, ecx
0x180085ad0  lea     rdx, aRaslinecloseWa_0; "RasLineClose: WaitForSingleObject faile"...
0x180085ad7  mov     word ptr [rsp+860h+var_830], cx
0x180085adc  mov     r8d, eax
0x180085adf  lea     rcx, [rsp+860h+var_830]
0x180085ae4  call    FormatRRASErrorString
0x180085ae9  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180085af0  lea     r8, [rsp+860h+var_830]
0x180085af5  mov     rcx, cs:gNdpspEtwContext
0x180085afc  mov     rax, cs:gNdpspTemplateFunc
0x180085b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b08  jmp     loc_180085E17
0x180085b0d  mov     ecx, cs:dwTraceId; dwTraceID
0x180085b13  cmp     ecx, edi
0x180085b15  jz      loc_180085E17
0x180085b1b  mov     r8d, ebx
0x180085b1e  lea     rdx, aRaslinecloseWa; "RasLineClose: WaitForSingleObject faile"...
0x180085b25  call    cs:__imp_TracePrintfA
0x180085b2b  jmp     loc_180085E17
0x180085b30  lea     rdx, [rsp+860h+var_838]
0x180085b35  mov     ecx, r14d
0x180085b38  call    GetLineObjWithWriteLock
0x180085b3d  mov     ebx, eax
0x180085b3f  test    eax, eax
0x180085b41  jz      short loc_180085BBA
0x180085b43  cmp     cs:gIsndpspEtwTracingAvailable, esi
0x180085b49  jz      short loc_180085B97
0x180085b4b  cmp     qword ptr cs:xmmword_1800C9BE0, rsi
0x180085b52  jz      loc_180085DF1
0x180085b58  xor     ecx, ecx
0x180085b5a  lea     rdx, aRaslinecloseGe_0; "RasLineClose: GetLineObjWithWriteLock f"...
0x180085b61  mov     word ptr [rsp+860h+var_830], cx
0x180085b66  mov     r8d, eax
0x180085b69  lea     rcx, [rsp+860h+var_830]
0x180085b6e  call    FormatRRASErrorString
0x180085b73  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180085b7a  lea     r8, [rsp+860h+var_830]
0x180085b7f  mov     rcx, cs:gNdpspEtwContext
0x180085b86  mov     rax, cs:gNdpspTemplateFunc
0x180085b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b92  jmp     loc_180085DF1
0x180085b97  mov     ecx, cs:dwTraceId; dwTraceID
0x180085b9d  cmp     ecx, edi
0x180085b9f  jz      loc_180085DF1
0x180085ba5  mov     r8d, eax
0x180085ba8  lea     rdx, aRaslinecloseGe; "RasLineClose: GetLineObjWithWriteLock f"...
0x180085baf  call    cs:__imp_TracePrintfA
0x180085bb5  jmp     loc_180085DF1
0x180085bba  mov     r15, [rsp+860h+var_838]
0x180085bbf  xor     edi, edi
0x180085bc1  mov     rax, cs:g_pRasOpenLines
0x180085bc8  mov     r12d, [r15+4]
0x180085bcc  jmp     short loc_180085BD7
0x180085bce  cmp     r12d, [rax+0Ch]
0x180085bd2  jz      short loc_180085BDE
0x180085bd4  mov     rax, [rax]
0x180085bd7  test    rax, rax
0x180085bda  jnz     short loc_180085BCE
0x180085bdc  jmp     short loc_180085BE1
0x180085bde  mov     rdi, rax
0x180085be1  cmp     cs:gIsndpspEtwTracingAvailable, esi
0x180085be7  jz      short loc_180085C32
0x180085be9  cmp     qword ptr cs:xmmword_1800C9BE0, rsi
0x180085bf0  jz      short loc_180085C51
0x180085bf2  xor     eax, eax
0x180085bf4  lea     rdx, aRaslinecloseRa_0; "RasLineClose: RasTapi line handle (%p)."...
0x180085bfb  mov     word ptr [rsp+860h+var_830], ax
0x180085c00  lea     rcx, [rsp+860h+var_830]
0x180085c05  mov     r9d, [rdi+14h]
0x180085c09  mov     r8d, r14d
0x180085c0c  call    FormatRRASErrorString
0x180085c11  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180085c18  lea     r8, [rsp+860h+var_830]
0x180085c1d  mov     rcx, cs:gNdpspEtwContext
0x180085c24  mov     rax, cs:gNdpspTemplateFunc
0x180085c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c30  jmp     short loc_180085C51
0x180085c32  mov     ecx, cs:dwTraceId; dwTraceID
0x180085c38  cmp     ecx, 0FFFFFFFFh
0x180085c3b  jz      short loc_180085C51
0x180085c3d  mov     r9d, [rdi+14h]
0x180085c41  lea     rdx, aRaslinecloseRa; "RasLineClose: RasTapi line handle (%p)."...
0x180085c48  mov     r8d, r14d
0x180085c4b  call    cs:__imp_TracePrintfA
0x180085c51  mov     eax, [rdi+14h]
0x180085c54  cmp     eax, 1
0x180085c57  ja      loc_180085DE4
0x180085c5d  lea     r9, [rsp+860h+lpInBuffer]
0x180085c62  mov     r8d, 10h
0x180085c68  mov     edx, r12d
0x180085c6b  mov     ecx, 7030103h
0x180085c70  call    PrepareSyncRequest
0x180085c75  mov     ebx, eax
0x180085c77  test    eax, eax
0x180085c79  jz      short loc_180085CF5
0x180085c7b  mov     ecx, r14d
0x180085c7e  call    ReleaseObjWriteLock
0x180085c83  cmp     cs:gIsndpspEtwTracingAvailable, esi
0x180085c89  jz      short loc_180085CD0
0x180085c8b  cmp     qword ptr cs:xmmword_1800C9BE0, rsi
0x180085c92  jz      short loc_180085CEB
0x180085c94  xor     eax, eax
0x180085c96  lea     rdx, aRaslineclosePr_0; "RasLineClose: PrepareSyncRequest failed"...
0x180085c9d  mov     r8d, ebx
0x180085ca0  mov     word ptr [rsp+860h+var_830], ax
0x180085ca5  lea     rcx, [rsp+860h+var_830]
0x180085caa  call    FormatRRASErrorString
0x180085caf  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180085cb6  lea     r8, [rsp+860h+var_830]
0x180085cbb  mov     rcx, cs:gNdpspEtwContext
0x180085cc2  mov     rax, cs:gNdpspTemplateFunc
0x180085cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085cce  jmp     short loc_180085CEB
0x180085cd0  mov     ecx, cs:dwTraceId; dwTraceID
0x180085cd6  cmp     ecx, 0FFFFFFFFh
0x180085cd9  jz      short loc_180085CEB
0x180085cdb  mov     r8d, ebx
0x180085cde  lea     rdx, aRaslineclosePr; "RasLineClose: PrepareSyncRequest failed"...
0x180085ce5  call    cs:__imp_TracePrintfA
0x180085ceb  mov     rsi, [rsp+860h+lpInBuffer]
0x180085cf0  jmp     loc_180085DF1
0x180085cf5  mov     rsi, [rsp+860h+lpInBuffer]
0x180085cfa  mov     ecx, 8FFF23CCh; dwIoControlCode
0x180085cff  mov     dword ptr [r15], 58585858h
0x180085d06  mov     rdx, rsi; lpInBuffer
0x180085d09  mov     rax, [r15+10h]
0x180085d0d  mov     [rsi+38h], rax
0x180085d11  call    SyncDriverRequest
0x180085d16  mov     ebx, eax
0x180085d18  test    eax, eax
0x180085d1a  jz      short loc_180085D86
0x180085d1c  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180085d23  jz      short loc_180085D6B
0x180085d25  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180085d2d  jz      short loc_180085D86
0x180085d2f  xor     eax, eax
0x180085d31  lea     rdx, aRaslinecloseSy; "RasLineClose: SyncDriverRequest(OID_TAP"...
0x180085d38  mov     r8d, ebx
0x180085d3b  mov     word ptr [rsp+860h+var_830], ax
0x180085d40  lea     rcx, [rsp+860h+var_830]
0x180085d45  call    FormatRRASErrorString
0x180085d4a  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180085d51  lea     r8, [rsp+860h+var_830]
0x180085d56  mov     rcx, cs:gNdpspEtwContext
0x180085d5d  mov     rax, cs:gNdpspTemplateFunc
0x180085d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085d69  jmp     short loc_180085D86
0x180085d6b  mov     ecx, cs:dwTraceId; dwTraceID
0x180085d71  cmp     ecx, 0FFFFFFFFh
0x180085d74  jz      short loc_180085D86
0x180085d76  mov     r8d, ebx
0x180085d79  lea     rdx, aRaslinecloseSy_0; "RasLineClose: SyncDriverRequest(OID_TAP"...
0x180085d80  call    cs:__imp_TracePrintfA
0x180085d86  mov     ecx, r14d
0x180085d89  call    ReleaseObjWriteLock
0x180085d8e  mov     ecx, r14d
0x180085d91  call    CloseObjHandle
0x180085d96  dec     dword ptr [rdi+14h]
0x180085d99  xor     ecx, ecx
0x180085d9b  mov     rdi, cs:g_pRasOpenLines
0x180085da2  test    rdi, rdi
0x180085da5  jz      short loc_180085DF1
0x180085da7  mov     rax, [rdi]
0x180085daa  cmp     r12d, [rdi+0Ch]
0x180085dae  jz      short loc_180085DBD
0x180085db0  mov     rcx, rdi
0x180085db3  mov     rdi, rax
0x180085db6  test    rax, rax
0x180085db9  jnz     short loc_180085DA7
0x180085dbb  jmp     short loc_180085DF1
0x180085dbd  test    rcx, rcx
0x180085dc0  jz      short loc_180085DC7
0x180085dc2  mov     [rcx], rax
0x180085dc5  jmp     short loc_180085DCE
0x180085dc7  mov     cs:g_pRasOpenLines, rax
0x180085dce  call    cs:__imp_GetProcessHeap
0x180085dd4  mov     r8, rdi; lpMem
0x180085dd7  xor     edx, edx; dwFlags
0x180085dd9  mov     rcx, rax; hHeap
0x180085ddc  call    cs:__imp_HeapFree
0x180085de2  jmp     short loc_180085DF1
0x180085de4  dec     eax
0x180085de6  mov     ecx, r14d
0x180085de9  mov     [rdi+14h], eax
0x180085dec  call    ReleaseObjWriteLock
0x180085df1  mov     rcx, cs:g_hRasOpenLinesMutex; hMutex
0x180085df8  call    cs:__imp_ReleaseMutex
0x180085dfe  test    rsi, rsi
0x180085e01  jz      short loc_180085E17
0x180085e03  call    cs:__imp_GetProcessHeap
0x180085e09  mov     r8, rsi; lpMem
0x180085e0c  xor     edx, edx; dwFlags
0x180085e0e  mov     rcx, rax; hHeap
0x180085e11  call    cs:__imp_HeapFree
0x180085e17  mov     eax, ebx
0x180085e19  mov     rcx, [rbp+760h+var_30]
0x180085e20  xor     rcx, rsp; StackCookie
0x180085e23  call    __security_check_cookie
0x180085e28  lea     r11, [rsp+860h+var_20]
0x180085e30  mov     rbx, [r11+38h]
0x180085e34  mov     rsi, [r11+40h]
0x180085e38  mov     rsp, r11
0x180085e3b  pop     r15
0x180085e3d  pop     r14
0x180085e3f  pop     r12
0x180085e41  pop     rdi
0x180085e42  pop     rbp
0x180085e43  retn
```
