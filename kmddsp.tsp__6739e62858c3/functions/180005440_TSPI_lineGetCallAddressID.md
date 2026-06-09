# TSPI_lineGetCallAddressID

- ea: `0x180005440`
- end: `0x18000553f`
- name: `TSPI_lineGetCallAddressID`
- size: `255`
- prototype: `LONG __stdcall(HDRVCALL hdCall, LPDWORD lpdwAddressID)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x180002494`
- `0x18000298c`
- `0x180003294`
- `0x180003890`
- `0x180003af0`
- `0x180004184`
- `0x180005440`
- `0x180007df8`

## string_xrefs

- `0x18000547d`: `lineGetCallAddressID(%d): call(%p)`
- `0x180005507`: `lineGetCallAddressID: addressID(%x)`

## pseudocode

```c
LONG __stdcall TSPI_lineGetCallAddressID(HDRVCALL hdCall, LPDWORD lpdwAddressID)
{
  LONG result; // eax
  __int64 v5; // rsi
  LONG v6; // edi
  _DWORD *v7; // rbx
  __int64 NdisTapiHandle; // rax
  DWORD v9; // r8d
  __int64 v10; // [rsp+50h] [rbp+18h] BYREF
  void *lpInBuffer; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  ++dword_18000E250;
  lpInBuffer = 0;
  TspLog(8, "lineGetCallAddressID(%d): call(%p)", dword_18000E250, hdCall);
  result = GetCallObjWithReadLock(hdCall, &v10);
  if ( !result )
  {
    v5 = v10;
    LODWORD(v10) = PrepareSyncRequest(117637389, *(_DWORD *)(v10 + 4), 0x18u, &lpInBuffer);
    v6 = v10;
    if ( !(_DWORD)v10 )
    {
      v7 = lpInBuffer;
      NdisTapiHandle = GetNdisTapiHandle(v5, &v10);
      v6 = v10;
      *((_QWORD *)v7 + 3) = NdisTapiHandle;
      if ( v6 )
      {
        FreeRequest(v7);
        return v6;
      }
      v6 = SyncDriverRequest(0x8FFF23C8, v7);
      if ( !v6 )
      {
        v9 = v7[8];
        *lpdwAddressID = v9;
        TspLog(4, "lineGetCallAddressID: addressID(%x)", v9);
      }
      FreeRequest(v7);
    }
    ReleaseObjReadLock(hdCall);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180005440  mov     rax, rsp
0x180005443  mov     [rax+8], rbx
0x180005447  mov     [rax+10h], rbp
0x18000544b  push    rsi
0x18000544c  push    rdi
0x18000544d  push    r14
0x18000544f  sub     rsp, 20h
0x180005453  mov     r8d, cs:dword_18000E250
0x18000545a  mov     r14, rdx
0x18000545d  inc     r8d
0x180005460  mov     qword ptr [rax+18h], 0
0x180005468  mov     rbp, rcx
0x18000546b  mov     cs:dword_18000E250, r8d
0x180005472  mov     r9, rcx
0x180005475  mov     qword ptr [rax+20h], 0
0x18000547d  lea     rdx, aLinegetcalladd_0; "lineGetCallAddressID(%d): call(%p)"
0x180005484  mov     ecx, 8
0x180005489  call    TspLog
0x18000548e  lea     rdx, [rsp+38h+arg_10]
0x180005493  mov     rcx, rbp
0x180005496  call    GetCallObjWithReadLock
0x18000549b  test    eax, eax
0x18000549d  jnz     loc_18000552B
0x1800054a3  mov     rsi, [rsp+38h+arg_10]
0x1800054a8  lea     r9, [rsp+38h+lpInBuffer]
0x1800054ad  lea     r8d, [rax+18h]
0x1800054b1  mov     ecx, 703010Dh
0x1800054b6  mov     edx, [rsi+4]
0x1800054b9  call    PrepareSyncRequest
0x1800054be  mov     dword ptr [rsp+38h+arg_10], eax
0x1800054c2  mov     edi, eax
0x1800054c4  test    eax, eax
0x1800054c6  jnz     short loc_180005521
0x1800054c8  mov     rbx, [rsp+38h+lpInBuffer]
0x1800054cd  lea     rdx, [rsp+38h+arg_10]
0x1800054d2  mov     rcx, rsi
0x1800054d5  call    GetNdisTapiHandle
0x1800054da  mov     edi, dword ptr [rsp+38h+arg_10]
0x1800054de  mov     [rbx+18h], rax
0x1800054e2  test    edi, edi
0x1800054e4  jz      short loc_1800054F0
0x1800054e6  mov     rcx, rbx; void *
0x1800054e9  call    FreeRequest
0x1800054ee  jmp     short loc_180005529
0x1800054f0  mov     rdx, rbx; lpInBuffer
0x1800054f3  mov     ecx, 8FFF23C8h; dwIoControlCode
0x1800054f8  call    SyncDriverRequest
0x1800054fd  mov     edi, eax
0x1800054ff  test    eax, eax
0x180005501  jnz     short loc_180005519
0x180005503  mov     r8d, [rbx+20h]
0x180005507  lea     rdx, aLinegetcalladd; "lineGetCallAddressID: addressID(%x)"
0x18000550e  lea     ecx, [rax+4]
0x180005511  mov     [r14], r8d
0x180005514  call    TspLog
0x180005519  mov     rcx, rbx; void *
0x18000551c  call    FreeRequest
0x180005521  mov     rcx, rbp
0x180005524  call    ReleaseObjReadLock
0x180005529  mov     eax, edi
0x18000552b  mov     rbx, [rsp+38h+arg_0]
0x180005530  mov     rbp, [rsp+38h+arg_8]
0x180005535  add     rsp, 20h
0x180005539  pop     r14
0x18000553b  pop     rdi
0x18000553c  pop     rsi
0x18000553d  retn
```
