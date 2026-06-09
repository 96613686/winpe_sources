# CLogStorage::PutWriteBuffer(CBuffer *)

- ea: `0x18000a990`
- end: `0x18000aa47`
- name: `?PutWriteBuffer@CLogStorage@@QEAAXPEAVCBuffer@@@Z`
- size: `183`
- prototype: `void __fastcall(CLogStorage *__hidden this, struct CBuffer *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d3ec`
- `0x180014254`
- `0x1800142b8`

## callees

- `0x18000a990`
- `0x18000d998`
- `0x18001266c`

## string_xrefs

- `0x18000a9dd`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000aa15`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
void __fastcall CLogStorage::PutWriteBuffer(CLogStorage *this, struct CBuffer *a2)
{
  ulong pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 12) )
  {
    TraceFile(-2147024809, "E_INVALIDARG", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x44Du);
    pExceptionObject = -2147024809;
    throw &pExceptionObject;
  }
  if ( *((_DWORD *)a2 + 16) )
  {
    if ( *((_QWORD *)this + 10) )
      *(_QWORD *)(*((_QWORD *)this + 11) + 48LL) = a2;
    else
      *((_QWORD *)this + 10) = a2;
    *((_QWORD *)this + 11) = a2;
    *((_QWORD *)a2 + 6) = 0;
  }
  else
  {
    if ( *((_DWORD *)a2 + 1) != *((_DWORD *)this + 10) )
    {
      TraceFile(-2147024809, "E_INVALIDARG", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x457u);
      pExceptionObject = -2147024809;
      throw &pExceptionObject;
    }
    *((_QWORD *)this + 12) = a2;
    *((_DWORD *)this + 7) = *(_DWORD *)a2;
  }
}

```

## disassembly

```asm
0x18000a990  sub     rsp, 28h
0x18000a994  xor     r8d, r8d
0x18000a997  cmp     [rcx+60h], r8
0x18000a99b  jnz     short loc_18000A9D7
0x18000a99d  cmp     [rdx+40h], r8d
0x18000a9a1  jnz     short loc_18000A9B6
0x18000a9a3  mov     eax, [rcx+28h]
0x18000a9a6  cmp     [rdx+4], eax
0x18000a9a9  jnz     short loc_18000AA0F
0x18000a9ab  mov     [rcx+60h], rdx
0x18000a9af  mov     eax, [rdx]
0x18000a9b1  mov     [rcx+1Ch], eax
0x18000a9b4  jmp     short loc_18000A9D2
0x18000a9b6  cmp     [rcx+50h], r8
0x18000a9ba  jnz     short loc_18000A9C2
0x18000a9bc  mov     [rcx+50h], rdx
0x18000a9c0  jmp     short loc_18000A9CA
0x18000a9c2  mov     rax, [rcx+58h]
0x18000a9c6  mov     [rax+30h], rdx
0x18000a9ca  mov     [rcx+58h], rdx
0x18000a9ce  mov     [rdx+30h], r8
0x18000a9d2  add     rsp, 28h
0x18000a9d6  retn
0x18000a9d7  mov     r9d, 44Dh; unsigned int
0x18000a9dd  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000a9e4  lea     rdx, aEInvalidarg; "E_INVALIDARG"
0x18000a9eb  mov     ecx, 80070057h; int
0x18000a9f0  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000a9f5  lea     rdx, _TI1K; pThrowInfo
0x18000a9fc  mov     [rsp+28h+pExceptionObject], 80070057h
0x18000aa04  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000aa09  call    _CxxThrowException_0
0x18000aa0f  mov     r9d, 457h; unsigned int
0x18000aa15  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000aa1c  lea     rdx, aEInvalidarg; "E_INVALIDARG"
0x18000aa23  mov     ecx, 80070057h; int
0x18000aa28  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000aa2d  lea     rdx, _TI1K; pThrowInfo
0x18000aa34  mov     [rsp+28h+pExceptionObject], 80070057h
0x18000aa3c  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000aa41  call    _CxxThrowException_0
```
