# EtwpGenerateHeaderEventForRealtime(ulong,_TRACE_LOGFILE_HEADER *,_SYSTEM_TRACE_HEADER * *,ulong *)

- ea: `0x18000ef18`
- end: `0x18000f091`
- name: `?EtwpGenerateHeaderEventForRealtime@@YAKKPEAU_TRACE_LOGFILE_HEADER@@PEAPEAU_SYSTEM_TRACE_HEADER@@PEAK@Z`
- size: `377`
- prototype: `unsigned int __fastcall(unsigned int, struct _TRACE_LOGFILE_HEADER *, struct _SYSTEM_TRACE_HEADER **, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180006c60`
- `0x180007060`

## callees

- `0x180001560`
- `0x180001eb2`
- `0x180001eca`
- `0x180001ee2`
- `0x180001ff0`
- `0x180002014`
- `0x18000ef18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000efd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000efd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efe0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efe0`

## pseudocode

```c
ULONG __fastcall EtwpGenerateHeaderEventForRealtime(
        int a1,
        struct _TRACE_LOGFILE_HEADER *a2,
        struct _SYSTEM_TRACE_HEADER **a3,
        unsigned int *a4)
{
  char *v7; // rax
  char *v8; // rdi
  NTSTATUS v9; // esi
  ULONG result; // eax
  _OWORD *v11; // rcx
  __int64 v12; // rax
  __int128 v13; // xmm1
  int v14; // [rsp+30h] [rbp-58h] BYREF
  int v15; // [rsp+38h] [rbp-50h] BYREF
  __int128 v16; // [rsp+40h] [rbp-48h] BYREF

  v15 = a1;
  v14 = 0;
  v16 = 0;
  v7 = (char *)operator new(0x13Cu, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
    return 14;
  memset_0(v7, 0, 0x13Cu);
  v9 = NtTraceControl_0(25, &v15, 4, &v16, 16, &v14);
  if ( v9 >= 0 )
  {
    *(_DWORD *)v8 = -1073610750;
    *((_DWORD *)v8 + 1) = 316;
    *((_QWORD *)v8 + 2) = *((_QWORD *)&v16 + 1);
    *((_DWORD *)v8 + 3) = GetCurrentProcessId();
    *((_DWORD *)v8 + 2) = GetCurrentThreadId();
    v11 = v8 + 32;
    v12 = 2;
    do
    {
      *v11 = *(_OWORD *)&a2->BufferSize;
      v11[1] = *(_OWORD *)&a2->EndTime.LowPart;
      v11[2] = *(_OWORD *)&a2->LogFileMode;
      v11[3] = *(_OWORD *)&a2->EventsLost;
      v11[4] = *(_OWORD *)&a2->LogFileName;
      v11[5] = *(_OWORD *)&a2->TimeZone.StandardName[2];
      v11[6] = *(_OWORD *)&a2->TimeZone.StandardName[10];
      v13 = *(_OWORD *)&a2->TimeZone.StandardName[18];
      a2 = (struct _TRACE_LOGFILE_HEADER *)((char *)a2 + 128);
      v11[7] = v13;
      v11 += 8;
      --v12;
    }
    while ( v12 );
    *v11 = *(_OWORD *)&a2->BufferSize;
    *((_QWORD *)v11 + 2) = a2->EndTime.QuadPart;
    *((_QWORD *)v8 + 37) = v16;
    result = 0;
    *((_DWORD *)v8 + 18) = 1;
    *a3 = (struct _SYSTEM_TRACE_HEADER *)v8;
    *a4 = 316;
  }
  else
  {
    operator delete(v8);
    return RtlNtStatusToDosError_0(v9);
  }
  return result;
}

```

## disassembly

```asm
0x18000ef18  mov     [rsp+arg_8], rbx
0x18000ef1d  push    rbp
0x18000ef1e  push    rsi
0x18000ef1f  push    rdi
0x18000ef20  push    r14
0x18000ef22  push    r15
0x18000ef24  sub     rsp, 60h
0x18000ef28  mov     rax, cs:__security_cookie
0x18000ef2f  xor     rax, rsp
0x18000ef32  mov     [rsp+88h+var_38], rax
0x18000ef37  mov     rbx, rdx
0x18000ef3a  mov     [rsp+88h+var_50], ecx
0x18000ef3e  xorps   xmm0, xmm0
0x18000ef41  mov     [rsp+88h+var_58], 0
0x18000ef49  mov     ebp, 13Ch
0x18000ef4e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ef55  mov     ecx, ebp; unsigned __int64
0x18000ef57  mov     r15, r9
0x18000ef5a  mov     r14, r8
0x18000ef5d  movups  [rsp+88h+var_48], xmm0
0x18000ef62  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ef67  mov     rdi, rax
0x18000ef6a  test    rax, rax
0x18000ef6d  jz      loc_18000F06B
0x18000ef73  mov     r8d, ebp; Size
0x18000ef76  xor     edx, edx; Val
0x18000ef78  mov     rcx, rax; void *
0x18000ef7b  call    memset_0
0x18000ef80  mov     r8d, 4
0x18000ef86  lea     rax, [rsp+88h+var_58]
0x18000ef8b  mov     [rsp+88h+var_60], rax
0x18000ef90  lea     r9, [rsp+88h+var_48]
0x18000ef95  lea     rdx, [rsp+88h+var_50]
0x18000ef9a  mov     [rsp+88h+var_68], 10h
0x18000efa2  lea     ecx, [r8+15h]
0x18000efa6  call    NtTraceControl_0
0x18000efab  mov     esi, eax
0x18000efad  test    eax, eax
0x18000efaf  jns     short loc_18000EFC5
0x18000efb1  mov     rcx, rdi; Block
0x18000efb4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000efb9  mov     ecx, esi; Status
0x18000efbb  call    RtlNtStatusToDosError_0
0x18000efc0  jmp     loc_18000F070
0x18000efc5  mov     dword ptr [rdi], 0C0020002h
0x18000efcb  mov     [rdi+4], ebp
0x18000efce  mov     rax, qword ptr [rsp+88h+var_48+8]
0x18000efd3  mov     [rdi+10h], rax
0x18000efd7  call    cs:__imp_GetCurrentProcessId
0x18000efdd  mov     [rdi+0Ch], eax
0x18000efe0  call    cs:__imp_GetCurrentThreadId
0x18000efe6  mov     [rdi+8], eax
0x18000efe9  lea     rcx, [rdi+20h]
0x18000efed  mov     eax, 2
0x18000eff2  lea     r8d, [rax+7Eh]
0x18000eff6  movups  xmm0, xmmword ptr [rbx]
0x18000eff9  movups  xmmword ptr [rcx], xmm0
0x18000effc  movups  xmm1, xmmword ptr [rbx+10h]
0x18000f000  movups  xmmword ptr [rcx+10h], xmm1
0x18000f004  movups  xmm0, xmmword ptr [rbx+20h]
0x18000f008  movups  xmmword ptr [rcx+20h], xmm0
0x18000f00c  movups  xmm1, xmmword ptr [rbx+30h]
0x18000f010  movups  xmmword ptr [rcx+30h], xmm1
0x18000f014  movups  xmm0, xmmword ptr [rbx+40h]
0x18000f018  movups  xmmword ptr [rcx+40h], xmm0
0x18000f01c  movups  xmm1, xmmword ptr [rbx+50h]
0x18000f020  movups  xmmword ptr [rcx+50h], xmm1
0x18000f024  movups  xmm0, xmmword ptr [rbx+60h]
0x18000f028  movups  xmmword ptr [rcx+60h], xmm0
0x18000f02c  movups  xmm1, xmmword ptr [rbx+70h]
0x18000f030  add     rbx, r8
0x18000f033  movups  xmmword ptr [rcx+70h], xmm1
0x18000f037  add     rcx, r8
0x18000f03a  sub     rax, 1
0x18000f03e  jnz     short loc_18000EFF6
0x18000f040  movups  xmm0, xmmword ptr [rbx]
0x18000f043  movups  xmmword ptr [rcx], xmm0
0x18000f046  mov     rax, [rbx+10h]
0x18000f04a  mov     [rcx+10h], rax
0x18000f04e  mov     rax, qword ptr [rsp+88h+var_48]
0x18000f053  mov     [rdi+128h], rax
0x18000f05a  xor     eax, eax
0x18000f05c  mov     dword ptr [rdi+48h], 1
0x18000f063  mov     [r14], rdi
0x18000f066  mov     [r15], ebp
0x18000f069  jmp     short loc_18000F070
0x18000f06b  mov     eax, 0Eh
0x18000f070  mov     rcx, [rsp+88h+var_38]
0x18000f075  xor     rcx, rsp; StackCookie
0x18000f078  call    __security_check_cookie
0x18000f07d  mov     rbx, [rsp+88h+arg_8]
0x18000f085  add     rsp, 60h
0x18000f089  pop     r15
0x18000f08b  pop     r14
0x18000f08d  pop     rdi
0x18000f08e  pop     rsi
0x18000f08f  pop     rbp
0x18000f090  retn
```
