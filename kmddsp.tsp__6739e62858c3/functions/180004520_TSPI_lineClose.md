# TSPI_lineClose

- ea: `0x180004520`
- end: `0x180004660`
- name: `TSPI_lineClose`
- size: `320`
- prototype: `LONG __stdcall(HDRVLINE hdLine)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001e40`
- `0x180002508`
- `0x18000298c`
- `0x180002ad0`
- `0x18000381c`
- `0x180003af0`
- `0x180004184`
- `0x180004520`
- `0x180007df8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180004617`
- `KERNEL32!LeaveCriticalSection` at `0x180004631`
- `KERNEL32!LeaveCriticalSection` at `0x180004617`
- `KERNEL32!LeaveCriticalSection` at `0x180004631`
- `KERNEL32!EnterCriticalSection` at `0x1800045fc`
- `KERNEL32!EnterCriticalSection` at `0x1800045fc`

## string_xrefs

- `0x1800045e0`: `DecommitNegotiatedTSPIVersion: deviceID(%x)`

## pseudocode

```c
LONG __stdcall TSPI_lineClose(HDRVLINE hdLine)
{
  LONG result; // eax
  __int64 v3; // r14
  LONG v4; // ebx
  _QWORD *v5; // rbx
  LONG v6; // edi
  unsigned int v7; // ebx
  __int64 LineDevNode; // rax
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF
  void *lpInBuffer; // [rsp+50h] [rbp+18h] BYREF

  v9 = 0;
  ++dword_18000E298;
  lpInBuffer = 0;
  TspLog(8, "lineClose(%d): line(%p)", dword_18000E298, hdLine);
  result = GetLineObjWithWriteLock(hdLine, &v9);
  if ( !result )
  {
    v3 = v9;
    v4 = PrepareSyncRequest(117637379, *(_DWORD *)(v9 + 4), 0x10u, &lpInBuffer);
    if ( v4 )
    {
      ReleaseObjWriteLock(hdLine);
      return v4;
    }
    else
    {
      v5 = lpInBuffer;
      *(_DWORD *)v3 = 1482184792;
      v5[3] = *(_QWORD *)(v3 + 16);
      v6 = SyncDriverRequest(0x8FFF23CC, v5);
      FreeRequest(v5);
      if ( !v6 )
      {
        v7 = *(_DWORD *)(v3 + 4);
        TspLog(8, "DecommitNegotiatedTSPIVersion: deviceID(%x)", v7);
        EnterCriticalSection(&stru_18000E3B0);
        LineDevNode = GetLineDevNode(v7);
        if ( LineDevNode )
        {
          *(_DWORD *)(LineDevNode + 24) = 0;
          LeaveCriticalSection(&stru_18000E3B0);
          v6 = 0;
        }
        else
        {
          LeaveCriticalSection(&stru_18000E3B0);
          v6 = -2147483580;
        }
      }
      ReleaseObjWriteLock(hdLine);
      CloseObjHandle(hdLine);
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004520  mov     [rsp+arg_0], rbx
0x180004525  push    rsi
0x180004526  push    rdi
0x180004527  push    r14
0x180004529  sub     rsp, 20h
0x18000452d  mov     r8d, cs:dword_18000E298
0x180004534  lea     rdx, aLinecloseDLine; "lineClose(%d): line(%p)"
0x18000453b  inc     r8d
0x18000453e  mov     [rsp+38h+arg_8], 0
0x180004547  mov     rsi, rcx
0x18000454a  mov     cs:dword_18000E298, r8d
0x180004551  mov     r9, rcx
0x180004554  mov     [rsp+38h+lpInBuffer], 0
0x18000455d  mov     ecx, 8
0x180004562  call    TspLog
0x180004567  lea     rdx, [rsp+38h+arg_8]
0x18000456c  mov     rcx, rsi
0x18000456f  call    GetLineObjWithWriteLock
0x180004574  test    eax, eax
0x180004576  jnz     loc_180004651
0x18000457c  mov     r14, [rsp+38h+arg_8]
0x180004581  lea     r9, [rsp+38h+lpInBuffer]
0x180004586  lea     r8d, [rax+10h]
0x18000458a  mov     ecx, 7030103h
0x18000458f  mov     edx, [r14+4]
0x180004593  call    PrepareSyncRequest
0x180004598  mov     ebx, eax
0x18000459a  test    eax, eax
0x18000459c  jz      short loc_1800045AD
0x18000459e  mov     rcx, rsi
0x1800045a1  call    ReleaseObjWriteLock
0x1800045a6  mov     eax, ebx
0x1800045a8  jmp     loc_180004651
0x1800045ad  mov     rbx, [rsp+38h+lpInBuffer]
0x1800045b2  mov     ecx, 8FFF23CCh; dwIoControlCode
0x1800045b7  mov     dword ptr [r14], 58585858h
0x1800045be  mov     rdx, rbx; lpInBuffer
0x1800045c1  mov     rax, [r14+10h]
0x1800045c5  mov     [rbx+18h], rax
0x1800045c9  call    SyncDriverRequest
0x1800045ce  mov     rcx, rbx; void *
0x1800045d1  mov     edi, eax
0x1800045d3  call    FreeRequest
0x1800045d8  test    edi, edi
0x1800045da  jnz     short loc_18000463F
0x1800045dc  mov     ebx, [r14+4]
0x1800045e0  lea     rdx, aDecommitnegoti; "DecommitNegotiatedTSPIVersion: deviceID"...
0x1800045e7  mov     r8d, ebx
0x1800045ea  lea     ecx, [rdi+8]
0x1800045ed  call    TspLog
0x1800045f2  lea     rdi, stru_18000E3B0
0x1800045f9  mov     rcx, rdi; lpCriticalSection
0x1800045fc  call    cs:__imp_EnterCriticalSection
0x180004603  nop     dword ptr [rax+rax+00h]
0x180004608  mov     ecx, ebx
0x18000460a  call    GetLineDevNode
0x18000460f  mov     rcx, rdi; lpCriticalSection
0x180004612  test    rax, rax
0x180004615  jnz     short loc_18000462A
0x180004617  call    cs:__imp_LeaveCriticalSection
0x18000461e  nop     dword ptr [rax+rax+00h]
0x180004623  mov     edi, 80000044h
0x180004628  jmp     short loc_18000463F
0x18000462a  mov     dword ptr [rax+18h], 0
0x180004631  call    cs:__imp_LeaveCriticalSection
0x180004638  nop     dword ptr [rax+rax+00h]
0x18000463d  xor     edi, edi
0x18000463f  mov     rcx, rsi
0x180004642  call    ReleaseObjWriteLock
0x180004647  mov     rcx, rsi
0x18000464a  call    CloseObjHandle
0x18000464f  mov     eax, edi
0x180004651  mov     rbx, [rsp+38h+arg_0]
0x180004656  add     rsp, 20h
0x18000465a  pop     r14
0x18000465c  pop     rdi
0x18000465d  pop     rsi
0x18000465e  retn
```
