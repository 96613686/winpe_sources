# TSPI_lineDevSpecific

- ea: `0x1800049a0`
- end: `0x180004b52`
- name: `TSPI_lineDevSpecific`
- size: `434`
- prototype: `LONG __stdcall(DRV_REQUESTID dwRequestID, HDRVLINE hdLine, DWORD dwAddressID, HDRVCALL hdCall, LPVOID lpParams, DWORD dwSize)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x180002494`
- `0x18000298c`
- `0x180002b6c`
- `0x180003294`
- `0x1800037a8`
- `0x180003890`
- `0x1800039f8`
- `0x1800049a0`
- `0x180007df8`
- `0x180008091`

## string_xrefs

- `0x1800049fc`: `lineDevSpecific(%d): reqID(%x), line(%p), addressID(%x), call(%p)`

## pseudocode

```c
LONG __stdcall TSPI_lineDevSpecific(
        DRV_REQUESTID dwRequestID,
        HDRVLINE hdLine,
        DWORD dwAddressID,
        HDRVCALL hdCall,
        LPVOID lpParams,
        DWORD dwSize)
{
  __int64 v6; // r14
  size_t v10; // r12
  unsigned int v11; // ebx
  LONG result; // eax
  __int64 v13; // r13
  LONG v14; // ebx
  _DWORD *v15; // rdi
  __int64 NdisTapiHandle; // rax
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF
  void *v18; // [rsp+48h] [rbp-20h] BYREF
  __int64 v19[3]; // [rsp+50h] [rbp-18h] BYREF

  v6 = 0;
  v17 = 0;
  v19[0] = 0;
  v18 = 0;
  TspLog(
    8,
    "lineDevSpecific(%d): reqID(%x), line(%p), addressID(%x), call(%p)",
    ++dword_18000E2A4,
    dwRequestID,
    hdLine,
    dwAddressID,
    hdCall);
  v10 = dwSize;
  if ( dwSize )
  {
    v11 = dwSize - 1 + 40;
    if ( v11 >= dwSize - 1 )
    {
      result = GetLineObjWithReadLock(hdLine, &v17);
      if ( result )
        return result;
      v13 = v17;
      v14 = PrepareAsyncRequest(117637383, *(_DWORD *)(v17 + 4), dwRequestID, v11, &v18);
      if ( v14 )
        goto LABEL_13;
      v15 = v18;
      *((_QWORD *)v18 + 16) = *(_QWORD *)(v13 + 16);
      v15[34] = dwAddressID;
      if ( hdCall )
      {
        dwSize = GetCallObjWithReadLock(hdCall, v19);
        v14 = dwSize;
        if ( dwSize )
        {
          FreeRequest(v15);
LABEL_13:
          ReleaseObjReadLock(hdLine);
          return v14;
        }
        v6 = v19[0];
        NdisTapiHandle = GetNdisTapiHandle(v19[0], &dwSize);
        v14 = dwSize;
        *((_QWORD *)v15 + 18) = NdisTapiHandle;
        if ( v14 )
        {
          FreeRequest(v15);
          return v14;
        }
      }
      else
      {
        *((_QWORD *)v15 + 18) = 0;
      }
      v15[38] = v10;
      memcpy_0(v15 + 39, lpParams, v10);
      *((_QWORD *)v15 + 12) = lpParams;
      *((_QWORD *)v15 + 5) = TSPI_lineDevSpecific_postProcess;
      v14 = AsyncDriverRequest(0x8FFF23C8, (char *)v15);
      if ( v6 )
        ReleaseObjReadLock(hdCall);
      goto LABEL_13;
    }
  }
  TspLog(1, "TSPI_lineDevSpecific: Arithmatic Overflow error %x", -2147024362);
  return 534;
}

```

## disassembly

```asm
0x1800049a0  mov     [rsp-40h+arg_10], r8d
0x1800049a5  push    rbp
0x1800049a6  push    rbx
0x1800049a7  push    rsi
0x1800049a8  push    rdi
0x1800049a9  push    r12
0x1800049ab  push    r13
0x1800049ad  push    r14
0x1800049af  push    r15
0x1800049b1  mov     rbp, rsp
0x1800049b4  sub     rsp, 68h
0x1800049b8  mov     eax, r8d
0x1800049bb  mov     [rsp+68h+var_38], r9
0x1800049c0  mov     r8d, cs:dword_18000E2A4
0x1800049c7  xor     r14d, r14d
0x1800049ca  mov     rsi, r9
0x1800049cd  mov     [rsp+68h+var_40], eax
0x1800049d1  mov     r15, rdx
0x1800049d4  mov     [rsp+68h+var_48], rdx
0x1800049d9  mov     edi, ecx
0x1800049db  mov     [rbp+var_28], 0
0x1800049e3  inc     r8d
0x1800049e6  mov     [rbp+var_18], r14
0x1800049ea  mov     r9d, ecx
0x1800049ed  mov     [rbp+var_20], r14
0x1800049f1  lea     ecx, [r14+8]
0x1800049f5  mov     cs:dword_18000E2A4, r8d
0x1800049fc  lea     rdx, aLinedevspecifi_0; "lineDevSpecific(%d): reqID(%x), line(%p"...
0x180004a03  call    TspLog
0x180004a08  mov     r12d, [rbp+dwSize]
0x180004a0c  cmp     r12d, 1
0x180004a10  jb      loc_180004B24
0x180004a16  lea     eax, [r12-1]
0x180004a1b  lea     ebx, [rax+28h]
0x180004a1e  cmp     ebx, eax
0x180004a20  jb      loc_180004B24
0x180004a26  lea     rdx, [rbp+var_28]
0x180004a2a  mov     rcx, r15
0x180004a2d  call    GetLineObjWithReadLock
0x180004a32  test    eax, eax
0x180004a34  jnz     loc_180004B40
0x180004a3a  mov     r13, [rbp+var_28]
0x180004a3e  lea     rax, [rbp+var_20]
0x180004a42  mov     r9d, ebx
0x180004a45  mov     [rsp+68h+var_48], rax
0x180004a4a  mov     r8d, edi
0x180004a4d  mov     ecx, 7030107h
0x180004a52  mov     edx, [r13+4]
0x180004a56  call    PrepareAsyncRequest
0x180004a5b  mov     ebx, eax
0x180004a5d  test    eax, eax
0x180004a5f  jnz     loc_180004B18
0x180004a65  mov     rax, [r13+10h]
0x180004a69  mov     rdi, [rbp+var_20]
0x180004a6d  mov     [rdi+80h], rax
0x180004a74  mov     eax, [rbp+arg_10]
0x180004a77  mov     [rdi+88h], eax
0x180004a7d  test    rsi, rsi
0x180004a80  jz      short loc_180004AC9
0x180004a82  lea     rdx, [rbp+var_18]
0x180004a86  mov     rcx, rsi
0x180004a89  call    GetCallObjWithReadLock
0x180004a8e  mov     [rbp+dwSize], eax
0x180004a91  mov     ebx, eax
0x180004a93  test    eax, eax
0x180004a95  jz      short loc_180004AA1
0x180004a97  mov     rcx, rdi; void *
0x180004a9a  call    FreeRequest
0x180004a9f  jmp     short loc_180004B18
0x180004aa1  mov     r14, [rbp+var_18]
0x180004aa5  lea     rdx, [rbp+dwSize]
0x180004aa9  mov     rcx, r14
0x180004aac  call    GetNdisTapiHandle
0x180004ab1  mov     ebx, [rbp+dwSize]
0x180004ab4  mov     [rdi+90h], rax
0x180004abb  test    ebx, ebx
0x180004abd  jz      short loc_180004AD0
0x180004abf  mov     rcx, rdi; void *
0x180004ac2  call    FreeRequest
0x180004ac7  jmp     short loc_180004B20
0x180004ac9  mov     [rdi+90h], r14
0x180004ad0  mov     rbx, [rbp+lpParams]
0x180004ad4  lea     rcx, [rdi+9Ch]; void *
0x180004adb  mov     rdx, rbx; Src
0x180004ade  mov     [rdi+98h], r12d
0x180004ae5  mov     r8, r12; Size
0x180004ae8  call    memcpy_0
0x180004aed  lea     rax, TSPI_lineDevSpecific_postProcess
0x180004af4  mov     [rdi+60h], rbx
0x180004af8  mov     rdx, rdi; void *
0x180004afb  mov     [rdi+28h], rax
0x180004aff  mov     ecx, 8FFF23C8h; dwIoControlCode
0x180004b04  call    AsyncDriverRequest
0x180004b09  mov     ebx, eax
0x180004b0b  test    r14, r14
0x180004b0e  jz      short loc_180004B18
0x180004b10  mov     rcx, rsi
0x180004b13  call    ReleaseObjReadLock
0x180004b18  mov     rcx, r15
0x180004b1b  call    ReleaseObjReadLock
0x180004b20  mov     eax, ebx
0x180004b22  jmp     short loc_180004B40
0x180004b24  mov     r8d, 80070216h
0x180004b2a  lea     rdx, aTspiLinedevspe_0; "TSPI_lineDevSpecific: Arithmatic Overfl"...
0x180004b31  mov     ecx, 1
0x180004b36  call    TspLog
0x180004b3b  mov     eax, 216h
0x180004b40  add     rsp, 68h
0x180004b44  pop     r15
0x180004b46  pop     r14
0x180004b48  pop     r13
0x180004b4a  pop     r12
0x180004b4c  pop     rdi
0x180004b4d  pop     rsi
0x180004b4e  pop     rbx
0x180004b4f  pop     rbp
0x180004b50  retn
```
