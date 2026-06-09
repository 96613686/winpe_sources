# CLogStorage::_GrovelDisk(CBuffer * *,CBuffer * *)

- ea: `0x18000b658`
- end: `0x18000b78f`
- name: `?_GrovelDisk@CLogStorage@@AEAAKPEAPEAVCBuffer@@0@Z`
- size: `311`
- prototype: `__int64 __fastcall(CLogStorage *this, struct CBuffer **, struct CBuffer **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a288`

## callees

- `0x18000b658`
- `0x18000b974`
- `0x18000c6b8`
- `0x18000d998`
- `0x18001266c`
- `0x180015010`

## string_xrefs

- `0x18000b754`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000b6f6`: `IDS_DTC_LOG_INCOMPATIBLE`

## pseudocode

```c
__int64 __fastcall CLogStorage::_GrovelDisk(CLogStorage *this, struct CBuffer **a2, struct CBuffer **a3)
{
  unsigned int v3; // esi
  unsigned int v5; // edi
  struct CBuffer *v8; // rax
  struct CBuffer *v9; // rbx
  _DWORD *v10; // rbp
  struct CBuffer *v11; // r15
  ulong v12; // edi
  char *v13; // rdx
  int v14; // ecx
  unsigned int v15; // r9d
  __int64 result; // rax
  ulong pExceptionObject; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0x2000;
  v5 = 0x2000;
  while ( 1 )
  {
    v8 = CLogStorage::_MapBuffer(this, v3, v5, 0, 0);
    v9 = v8;
    v10 = (_DWORD *)*((_QWORD *)v8 + 3);
    if ( !v10 )
    {
      v12 = -2147024809;
      v13 = "E_INVALIDARG";
      v14 = -2147024809;
      v15 = 1550;
LABEL_10:
      TraceFile(v14, v13, "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", v15);
      if ( v9 )
        CLogStorage::_UnmapBuffer(this, v9, 0);
      pExceptionObject = v12;
      throw &pExceptionObject;
    }
    v11 = v8;
    if ( *v10 == 1381258066
      && v10[20] == v5
      && (unsigned int)((__int64 (__fastcall *)(_QWORD, _DWORD *, void *))lpCalcCRC)(
                         (unsigned int)(*((_DWORD *)this + 10) - 8),
                         v10 + 2,
                         pulCRCTable) == v10[1] )
    {
      break;
    }
    v9 = 0;
    CLogStorage::_UnmapBuffer(this, v11, 0);
    v3 += v5;
    v5 *= 2;
    if ( v3 > 0x4000 )
    {
      v12 = -1073737662;
      v13 = "IDS_DTC_LOG_INCOMPATIBLE";
      v14 = -1073737662;
      v15 = 1618;
      goto LABEL_10;
    }
  }
  *a2 = CLogStorage::_MapBuffer(this, 0, v5, 0, 0);
  result = v5;
  *a3 = v9;
  return result;
}

```

## disassembly

```asm
0x18000b658  push    rbx
0x18000b65a  push    rbp
0x18000b65b  push    rsi
0x18000b65c  push    rdi
0x18000b65d  push    r12
0x18000b65f  push    r13
0x18000b661  push    r14
0x18000b663  push    r15
0x18000b665  sub     rsp, 38h
0x18000b669  mov     esi, 2000h
0x18000b66e  mov     r12, r8
0x18000b671  mov     edi, esi
0x18000b673  mov     r13, rdx
0x18000b676  mov     r14, rcx
0x18000b679  xor     r9d, r9d; int
0x18000b67c  mov     [rsp+78h+var_58], 0; unsigned int
0x18000b684  mov     r8d, edi; unsigned int
0x18000b687  mov     edx, esi; unsigned int
0x18000b689  mov     rcx, r14; this
0x18000b68c  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000b691  mov     rbx, rax
0x18000b694  mov     rbp, [rax+18h]
0x18000b698  test    rbp, rbp
0x18000b69b  jz      loc_18000B73D
0x18000b6a1  cmp     dword ptr [rbp+0], 52545352h
0x18000b6a8  mov     r15, rax
0x18000b6ab  jnz     short loc_18000B6D5
0x18000b6ad  cmp     [rbp+50h], edi
0x18000b6b0  jnz     short loc_18000B6D5
0x18000b6b2  mov     ecx, [r14+28h]
0x18000b6b6  lea     rdx, [rbp+8]
0x18000b6ba  mov     r8, cs:?pulCRCTable@@3PEAKEA; ulong * pulCRCTable
0x18000b6c1  sub     ecx, 8
0x18000b6c4  mov     rax, cs:?lpCalcCRC@@3P6AKIPEAEPEAK@ZEA; ulong (*lpCalcCRC)(uint,uchar *,ulong *)
0x18000b6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6d0  cmp     eax, [rbp+4]
0x18000b6d3  jz      short loc_18000B70A
0x18000b6d5  xor     r8d, r8d; int
0x18000b6d8  mov     rdx, r15; struct CBuffer *
0x18000b6db  mov     rcx, r14; this
0x18000b6de  xor     ebx, ebx
0x18000b6e0  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18000b6e5  add     esi, edi
0x18000b6e7  add     edi, edi
0x18000b6e9  cmp     esi, 4000h
0x18000b6ef  jbe     short loc_18000B679
0x18000b6f1  mov     edi, 0C0001042h
0x18000b6f6  lea     rdx, aIdsDtcLogIncom; "IDS_DTC_LOG_INCOMPATIBLE"
0x18000b6fd  mov     ecx, 0C0001042h
0x18000b702  mov     r9d, 652h
0x18000b708  jmp     short loc_18000B754
0x18000b70a  xor     r9d, r9d; int
0x18000b70d  mov     [rsp+78h+var_58], 0; unsigned int
0x18000b715  mov     r8d, edi; unsigned int
0x18000b718  xor     edx, edx; unsigned int
0x18000b71a  mov     rcx, r14; this
0x18000b71d  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000b722  mov     [r13+0], rax
0x18000b726  mov     eax, edi
0x18000b728  mov     [r12], rbx
0x18000b72c  add     rsp, 38h
0x18000b730  pop     r15
0x18000b732  pop     r14
0x18000b734  pop     r13
0x18000b736  pop     r12
0x18000b738  pop     rdi
0x18000b739  pop     rsi
0x18000b73a  pop     rbp
0x18000b73b  pop     rbx
0x18000b73c  retn
0x18000b73d  mov     edi, 80070057h
0x18000b742  lea     rdx, aEInvalidarg; "E_INVALIDARG"
0x18000b749  mov     ecx, 80070057h; int
0x18000b74e  mov     r9d, 60Eh; unsigned int
0x18000b754  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000b75b  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000b760  test    rbx, rbx
0x18000b763  jz      short loc_18000B773
0x18000b765  xor     r8d, r8d; int
0x18000b768  mov     rdx, rbx; struct CBuffer *
0x18000b76b  mov     rcx, r14; this
0x18000b76e  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18000b773  lea     rdx, _TI1K; pThrowInfo
0x18000b77a  mov     [rsp+78h+pExceptionObject], edi
0x18000b781  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000b789  call    _CxxThrowException_0
```
