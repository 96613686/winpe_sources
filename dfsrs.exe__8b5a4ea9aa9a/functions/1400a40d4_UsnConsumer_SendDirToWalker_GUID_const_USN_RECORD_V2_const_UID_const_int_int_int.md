# UsnConsumer::SendDirToWalker(_GUID const &,USN_RECORD_V2 const &,UID const &,int,int,int)

- ea: `0x1400a40d4`
- end: `0x1400a4506`
- name: `?SendDirToWalker@UsnConsumer@@AEAAPEAVFrsStatus@@AEBU_GUID@@AEBUUSN_RECORD_V2@@AEBVUID@@HHH@Z`
- size: `1074`
- prototype: `struct FrsStatus *__usercall@<rax>(UsnConsumer *__hidden this@<rcx>, const struct _GUID *@<rdx>, const struct USN_RECORD_V2 *@<r8>, const struct UID *@<r9>, int, int, int)`
- caller_count: `5`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x1400a0e34`
- `0x1400a2794`
- `0x1400a2d5c`
- `0x1400a48c4`
- `0x1400a6460`

## callees

- `0x1400036a0`
- `0x14000d980`
- `0x14000dcc0`
- `0x140024be4`
- `0x140028fcc`
- `0x140097604`
- `0x14009a000`
- `0x14009a288`
- `0x14009fd58`
- `0x1400a05b8`
- `0x1400a40d4`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1400a443c`
- `KERNEL32!WaitForSingleObject` at `0x1400a443c`
- `KERNEL32!LeaveCriticalSection` at `0x1400a4426`
- `KERNEL32!LeaveCriticalSection` at `0x1400a4426`
- `KERNEL32!EnterCriticalSection` at `0x1400a444b`
- `KERNEL32!EnterCriticalSection` at `0x1400a444b`
- `KERNEL32!GetCurrentThreadId` at `0x1400a41a1`
- `KERNEL32!GetCurrentThreadId` at `0x1400a41f3`
- `KERNEL32!GetCurrentThreadId` at `0x1400a42ee`
- `KERNEL32!GetCurrentThreadId` at `0x1400a43c8`
- `KERNEL32!GetCurrentThreadId` at `0x1400a4463`
- `KERNEL32!GetCurrentThreadId` at `0x1400a41a1`
- `KERNEL32!GetCurrentThreadId` at `0x1400a41f3`
- `KERNEL32!GetCurrentThreadId` at `0x1400a42ee`
- `KERNEL32!GetCurrentThreadId` at `0x1400a43c8`
- `KERNEL32!GetCurrentThreadId` at `0x1400a4463`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct FrsStatus *__fastcall UsnConsumer::SendDirToWalker(
        UsnConsumer *this,
        struct _GUID *a2,
        const struct USN_RECORD_V2 *a3,
        const struct UID *a4,
        int a5,
        int a6,
        int a7)
{
  const struct USN_RECORD_V2 *v8; // rdi
  const union _LARGE_INTEGER *p_TimeStamp; // rbx
  unsigned int *v11; // rdi
  DWORD v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdi
  struct FrsStatus *v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // rcx
  const unsigned __int16 *v18; // rax
  DWORD v19; // eax
  __int64 v20; // rdx
  int v21; // ecx
  struct FrsStatus *v22; // rbx
  DWORD v23; // eax
  __int64 v24; // rcx
  DirWalkerTask *i; // rbx
  void *v27; // [rsp+48h] [rbp-99h]
  const struct UID *v28; // [rsp+68h] [rbp-79h] BYREF
  unsigned int *FileReferenceNumber; // [rsp+70h] [rbp-71h] BYREF
  struct _GUID *v30; // [rsp+78h] [rbp-69h]
  _QWORD v31[2]; // [rsp+80h] [rbp-61h] BYREF
  __int128 v32; // [rsp+90h] [rbp-51h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-41h]
  union _LARGE_INTEGER v34; // [rsp+A8h] [rbp-39h]
  __int64 v35; // [rsp+B0h] [rbp-31h]
  _BYTE v36[32]; // [rsp+B8h] [rbp-29h] BYREF

  v28 = a4;
  v8 = a3;
  v31[0] = a3;
  v30 = a2;
  std::wstring::wstring(v36, a3->FileName, (unsigned __int64)a3->FileNameLength >> 1);
  v32 = 0;
  v33 = 0;
  p_TimeStamp = &v8->TimeStamp;
  if ( a5 )
  {
    if ( a7
      || (v32 = *(_OWORD *)a4,
          v33 = *((_QWORD *)a4 + 2),
          v34 = *p_TimeStamp,
          v35 = 1,
          (v11 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD))(**((_QWORD **)this + 13) + 240LL))(
                                   *((_QWORD *)this + 13),
                                   &v32,
                                   0)) == 0)
      || (v12 = GetCurrentThreadId(),
          (v14 = FrsStatusList::PushNewError(
                   v13,
                   v11[1],
                   v11[2],
                   *v11,
                   "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                   "UsnConsumer::SendDirToWalker",
                   3319,
                   v12,
                   v11)) == 0) )
    {
      v15 = UsnConsumer::CheckPoint(this);
      if ( !v15 )
      {
        v14 = 0;
LABEL_9:
        v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
        v28 = *(const struct UID **)(v31[0] + 8LL);
        DirWalkerTask::QueueMoveinJob(
          *((DirWalkerTask **)this + 27),
          v30,
          (const struct FileId *)&v28,
          v18,
          p_TimeStamp,
          a4,
          0,
          0,
          a7,
          v27,
          0);
        goto LABEL_27;
      }
      CurrentThreadId = GetCurrentThreadId();
      v14 = FrsStatusList::PushNewError(
              v17,
              *((unsigned int *)v15 + 1),
              *((unsigned int *)v15 + 2),
              *(unsigned int *)v15,
              "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
              "UsnConsumer::SendDirToWalker",
              3325,
              CurrentThreadId,
              v15);
      if ( !v14 )
        goto LABEL_9;
    }
  }
  else
  {
    if ( !a7 )
    {
      v32 = *(_OWORD *)v28;
      v33 = *((_QWORD *)v28 + 2);
      v34 = *p_TimeStamp;
      LODWORD(v35) = 2;
      HIDWORD(v35) = a6 != 0 ? 2 : 0;
      FileReferenceNumber = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD))(**((_QWORD **)this + 13)
                                                                                                  + 240LL))(
                                              *((_QWORD *)this + 13),
                                              &v32,
                                              0);
      if ( FileReferenceNumber )
      {
        v19 = GetCurrentThreadId();
        v14 = FrsStatusList::PushNewError(
                FileReferenceNumber,
                FileReferenceNumber[1],
                FileReferenceNumber[2],
                *FileReferenceNumber,
                "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                "UsnConsumer::SendDirToWalker",
                3345,
                v19,
                FileReferenceNumber);
        if ( v14 )
          goto LABEL_27;
        v8 = (const struct USN_RECORD_V2 *)v31[0];
      }
    }
    ScopedLock::ScopedLock((ScopedLock *)v31, (struct ScopedCS *)(*((_QWORD *)this + 27) + 344LL));
    v20 = *((_QWORD *)this + 28);
    if ( a7 )
      v21 = 1;
    else
      v21 = a6 != 0 ? 2 : 0;
    FileReferenceNumber = (unsigned int *)v8->FileReferenceNumber;
    DirWalkerTask::QueueMoveoutJob(*((_QWORD *)this + 27), p_TimeStamp, v28, v30, &FileReferenceNumber, 0, 0, v21, v20);
    v22 = UsnConsumer::CheckPoint(this);
    if ( v22 )
    {
      v23 = GetCurrentThreadId();
      v14 = FrsStatusList::PushNewError(
              v24,
              *((unsigned int *)v22 + 1),
              *((unsigned int *)v22 + 2),
              *(unsigned int *)v22,
              "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
              "UsnConsumer::SendDirToWalker",
              3375,
              v23,
              v22);
    }
    else
    {
      v14 = 0;
    }
    ScopedLock::~ScopedLock((ScopedLock *)v31);
    if ( TaskPool::g_threaded == 1 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
      WaitForSingleObject(*((HANDLE *)this + 28), 0xFFFFFFFF);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    }
    else
    {
      for ( i = (DirWalkerTask *)*((_QWORD *)this + 27);
            *((_QWORD *)i + 38);
            (*(void (__fastcall **)(DirWalkerTask *))(*(_QWORD *)i + 16LL))(i) )
      {
        ;
      }
      if ( *((_QWORD *)i + 56) )
        DirWalkerTask::CheckPoint(i, 0, 1);
    }
  }
LABEL_27:
  std::wstring::~wstring(v36);
  return (struct FrsStatus *)v14;
}

```

## disassembly

```asm
0x1400a40d4  push    rbp
0x1400a40d6  push    rbx
0x1400a40d7  push    rsi
0x1400a40d8  push    rdi
0x1400a40d9  push    r12
0x1400a40db  push    r13
0x1400a40dd  push    r14
0x1400a40df  push    r15
0x1400a40e1  lea     rbp, [rsp-7]
0x1400a40e6  sub     rsp, 0E8h
0x1400a40ed  mov     rax, cs:__security_cookie
0x1400a40f4  xor     rax, rsp
0x1400a40f7  mov     [rbp+3Fh+var_48], rax
0x1400a40fb  mov     r13, r9
0x1400a40fe  mov     [rbp+3Fh+var_B8], r9
0x1400a4102  mov     rdi, r8
0x1400a4105  mov     [rbp+3Fh+var_A0], r8
0x1400a4109  mov     [rbp+3Fh+var_A8], rdx
0x1400a410d  mov     rsi, rcx
0x1400a4110  movzx   r8d, word ptr [r8+38h]
0x1400a4115  shr     r8, 1
0x1400a4118  lea     rdx, [rdi+3Ch]
0x1400a411c  lea     rcx, [rbp+3Fh+var_68]
0x1400a4120  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1400a4125  nop
0x1400a4126  xorps   xmm0, xmm0
0x1400a4129  movups  [rbp+3Fh+var_90], xmm0
0x1400a412d  xor     ecx, ecx
0x1400a412f  mov     [rbp+3Fh+var_80], rcx
0x1400a4133  lea     edx, [rcx+1]
0x1400a4136  mov     [rsp+120h+var_C0], edx
0x1400a413a  lea     rbx, [rdi+20h]
0x1400a413e  lea     r14, aUsnconsumerSen; "UsnConsumer::SendDirToWalker"
0x1400a4145  lea     r15, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a414c  cmp     [rbp+3Fh+arg_20], ecx
0x1400a414f  jz      loc_1400A428B
0x1400a4155  mov     r12d, [rbp+3Fh+arg_30]
0x1400a4159  test    r12d, r12d
0x1400a415c  jnz     loc_1400A41E3
0x1400a4162  movups  xmm0, xmmword ptr [r13+0]
0x1400a4167  movdqu  [rbp+3Fh+var_90], xmm0
0x1400a416c  mov     rax, [r13+10h]
0x1400a4170  mov     [rbp+3Fh+var_80], rax
0x1400a4174  mov     rax, [rbx]
0x1400a4177  mov     [rbp+3Fh+var_78], rax
0x1400a417b  mov     [rbp+3Fh+var_70], rdx
0x1400a417f  mov     rcx, [rsi+68h]
0x1400a4183  mov     rax, [rcx]
0x1400a4186  xor     r8d, r8d
0x1400a4189  lea     rdx, [rbp+3Fh+var_90]
0x1400a418d  mov     rax, [rax+0F0h]
0x1400a4194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4199  mov     rdi, rax
0x1400a419c  test    rax, rax
0x1400a419f  jz      short loc_1400A41E3
0x1400a41a1  call    cs:__imp_GetCurrentThreadId
0x1400a41a8  nop     dword ptr [rax+rax+00h]
0x1400a41ad  mov     qword ptr [rsp+120h+var_E0], rdi
0x1400a41b2  mov     dword ptr [rsp+120h+var_E8], eax; struct Usn *
0x1400a41b6  mov     dword ptr [rsp+120h+var_F0], 0CF7h; struct _FILETIME *
0x1400a41be  mov     [rsp+120h+var_F8], r14
0x1400a41c3  mov     [rsp+120h+var_100], r15
0x1400a41c8  mov     r9d, [rdi]
0x1400a41cb  mov     r8d, [rdi+8]
0x1400a41cf  mov     edx, [rdi+4]
0x1400a41d2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a41d7  mov     rdi, rax
0x1400a41da  test    rax, rax
0x1400a41dd  jnz     loc_1400A44D9
0x1400a41e3  mov     rcx, rsi; this
0x1400a41e6  call    ?CheckPoint@UsnConsumer@@AEAAPEAVFrsStatus@@XZ; UsnConsumer::CheckPoint(void)
0x1400a41eb  mov     rdi, rax
0x1400a41ee  test    rax, rax
0x1400a41f1  jz      short loc_1400A4237
0x1400a41f3  call    cs:__imp_GetCurrentThreadId
0x1400a41fa  nop     dword ptr [rax+rax+00h]
0x1400a41ff  mov     qword ptr [rsp+120h+var_E0], rdi
0x1400a4204  mov     dword ptr [rsp+120h+var_E8], eax
0x1400a4208  mov     dword ptr [rsp+120h+var_F0], 0CFDh
0x1400a4210  mov     [rsp+120h+var_F8], r14
0x1400a4215  mov     [rsp+120h+var_100], r15
0x1400a421a  mov     r9d, [rdi]
0x1400a421d  mov     r8d, [rdi+8]
0x1400a4221  mov     edx, [rdi+4]
0x1400a4224  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a4229  mov     rdi, rax
0x1400a422c  test    rax, rax
0x1400a422f  jnz     loc_1400A44D9
0x1400a4235  jmp     short loc_1400A4239
0x1400a4237  xor     edi, edi
0x1400a4239  lea     rcx, [rbp+3Fh+var_68]
0x1400a423d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400a4242  mov     rcx, [rbp+3Fh+var_A0]
0x1400a4246  mov     rcx, [rcx+8]
0x1400a424a  mov     [rbp+3Fh+var_B8], rcx
0x1400a424e  and     [rsp+120h+var_D0], 0
0x1400a4254  mov     [rsp+120h+var_E0], r12d; int
0x1400a4259  and     [rsp+120h+var_E8], 0
0x1400a425f  and     [rsp+120h+var_F0], 0
0x1400a4265  mov     [rsp+120h+var_F8], r13; struct UID *
0x1400a426a  mov     [rsp+120h+var_100], rbx; union _LARGE_INTEGER *
0x1400a426f  mov     r9, rax; unsigned __int16 *
0x1400a4272  lea     r8, [rbp+3Fh+var_B8]; struct FileId *
0x1400a4276  mov     rdx, [rbp+3Fh+var_A8]; struct _GUID *
0x1400a427a  mov     rcx, [rsi+0D8h]; this
0x1400a4281  call    ?QueueMoveinJob@DirWalkerTask@@QEAAXAEBU_GUID@@AEBVFileId@@PEBGAEBT_LARGE_INTEGER@@AEBVUID@@PEBU_FILETIME@@PEBVUsn@@HPEAXPEAVContentSetManager@@@Z; DirWalkerTask::QueueMoveinJob(_GUID const &,FileId const &,ushort const *,_LARGE_INTEGER const &,UID const &,_FILETIME const *,Usn const *,int,void *,ContentSetManager *)
0x1400a4286  jmp     loc_1400A44D9
0x1400a428b  mov     r12d, [rbp+3Fh+arg_28]
0x1400a428f  mov     r13d, [rbp+3Fh+arg_30]
0x1400a4293  test    r13d, r13d
0x1400a4296  jnz     loc_1400A4338
0x1400a429c  mov     rax, [rbp+3Fh+var_B8]
0x1400a42a0  movups  xmm0, xmmword ptr [rax]
0x1400a42a3  movdqu  [rbp+3Fh+var_90], xmm0
0x1400a42a8  mov     rax, [rax+10h]
0x1400a42ac  mov     [rbp+3Fh+var_80], rax
0x1400a42b0  mov     rax, [rbx]
0x1400a42b3  mov     [rbp+3Fh+var_78], rax
0x1400a42b7  mov     dword ptr [rbp+3Fh+var_70], 2
0x1400a42be  mov     eax, r12d
0x1400a42c1  neg     eax
0x1400a42c3  sbb     ecx, ecx
0x1400a42c5  and     ecx, 2
0x1400a42c8  mov     dword ptr [rbp+3Fh+var_70+4], ecx
0x1400a42cb  mov     rcx, [rsi+68h]
0x1400a42cf  mov     rax, [rcx]
0x1400a42d2  xor     r8d, r8d
0x1400a42d5  lea     rdx, [rbp+3Fh+var_90]
0x1400a42d9  mov     rax, [rax+0F0h]
0x1400a42e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a42e5  mov     [rbp+3Fh+var_B0], rax
0x1400a42e9  test    rax, rax
0x1400a42ec  jz      short loc_1400A4338
0x1400a42ee  call    cs:__imp_GetCurrentThreadId
0x1400a42f5  nop     dword ptr [rax+rax+00h]
0x1400a42fa  mov     rcx, [rbp+3Fh+var_B0]
0x1400a42fe  mov     qword ptr [rsp+120h+var_E0], rcx
0x1400a4303  mov     dword ptr [rsp+120h+var_E8], eax
0x1400a4307  mov     dword ptr [rsp+120h+var_F0], 0D11h
0x1400a430f  mov     [rsp+120h+var_F8], r14
0x1400a4314  mov     [rsp+120h+var_100], r15
0x1400a4319  mov     r9d, [rcx]
0x1400a431c  mov     r8d, [rcx+8]
0x1400a4320  mov     edx, [rcx+4]
0x1400a4323  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a4328  mov     rdi, rax
0x1400a432b  test    rax, rax
0x1400a432e  jnz     loc_1400A44D9
0x1400a4334  mov     rdi, [rbp+3Fh+var_A0]
0x1400a4338  mov     rdx, [rsi+0D8h]
0x1400a433f  add     rdx, 158h; struct ScopedCS *
0x1400a4346  lea     rcx, [rbp+3Fh+var_A0]; this
0x1400a434a  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x1400a434f  nop
0x1400a4350  mov     rdx, [rsi+0E0h]
0x1400a4357  test    r13d, r13d
0x1400a435a  jz      short loc_1400A4363
0x1400a435c  mov     ecx, 1
0x1400a4361  jmp     short loc_1400A436B
0x1400a4363  neg     r12d
0x1400a4366  sbb     ecx, ecx
0x1400a4368  and     ecx, 2
0x1400a436b  mov     rax, [rdi+8]
0x1400a436f  mov     [rbp+3Fh+var_B0], rax
0x1400a4373  lea     rax, [rsp+120h+var_C0]
0x1400a4378  mov     [rsp+120h+var_D0], rax
0x1400a437d  xor     r12d, r12d
0x1400a4380  mov     dword ptr [rsp+120h+var_D8], r12d
0x1400a4385  mov     qword ptr [rsp+120h+var_E0], rdx
0x1400a438a  mov     dword ptr [rsp+120h+var_E8], ecx
0x1400a438e  mov     dword ptr [rsp+120h+var_F0], r12d
0x1400a4393  mov     dword ptr [rsp+120h+var_F8], r12d
0x1400a4398  lea     rax, [rbp+3Fh+var_B0]
0x1400a439c  mov     [rsp+120h+var_100], rax
0x1400a43a1  mov     r9, [rbp+3Fh+var_A8]
0x1400a43a5  mov     r8, [rbp+3Fh+var_B8]
0x1400a43a9  mov     rdx, rbx
0x1400a43ac  mov     rcx, [rsi+0D8h]
0x1400a43b3  call    ?QueueMoveoutJob@DirWalkerTask@@QEAAXAEBT_LARGE_INTEGER@@AEBVUID@@AEBU_GUID@@AEBVFileId@@HHW4MOVEOUT_TYPE@@PEAXHPEAH@Z; DirWalkerTask::QueueMoveoutJob(_LARGE_INTEGER const &,UID const &,_GUID const &,FileId const &,int,int,MOVEOUT_TYPE,void *,int,int *)
0x1400a43b8  mov     rcx, rsi; this
0x1400a43bb  call    ?CheckPoint@UsnConsumer@@AEAAPEAVFrsStatus@@XZ; UsnConsumer::CheckPoint(void)
0x1400a43c0  mov     rbx, rax
0x1400a43c3  test    rax, rax
0x1400a43c6  jz      short loc_1400A4403
0x1400a43c8  call    cs:__imp_GetCurrentThreadId
0x1400a43cf  nop     dword ptr [rax+rax+00h]
0x1400a43d4  mov     qword ptr [rsp+120h+var_E0], rbx
0x1400a43d9  mov     dword ptr [rsp+120h+var_E8], eax
0x1400a43dd  mov     dword ptr [rsp+120h+var_F0], 0D2Fh
0x1400a43e5  mov     [rsp+120h+var_F8], r14
0x1400a43ea  mov     [rsp+120h+var_100], r15
0x1400a43ef  mov     r9d, [rbx]
0x1400a43f2  mov     r8d, [rbx+8]
0x1400a43f6  mov     edx, [rbx+4]
0x1400a43f9  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a43fe  mov     rdi, rax
0x1400a4401  jmp     short loc_1400A4406
0x1400a4403  mov     rdi, r12
0x1400a4406  lea     rcx, [rbp+3Fh+var_A0]; this
0x1400a440a  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x1400a440f  cmp     cs:?g_threaded@TaskPool@@0HA, 1; int TaskPool::g_threaded
0x1400a4416  jnz     loc_1400A44A0
0x1400a441c  lea     rbx, [rsi+0E8h]
0x1400a4423  mov     rcx, rbx; lpCriticalSection
0x1400a4426  call    cs:__imp_LeaveCriticalSection
0x1400a442d  nop     dword ptr [rax+rax+00h]
0x1400a4432  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400a4435  mov     rcx, [rsi+0E0h]; hHandle
0x1400a443c  call    cs:__imp_WaitForSingleObject
0x1400a4443  nop     dword ptr [rax+rax+00h]
0x1400a4448  mov     rcx, rbx; lpCriticalSection
0x1400a444b  call    cs:__imp_EnterCriticalSection
0x1400a4452  nop     dword ptr [rax+rax+00h]
0x1400a4457  test    rdi, rdi
0x1400a445a  jnz     short loc_1400A44D9
0x1400a445c  cmp     [rsp+120h+var_C0], r12d
0x1400a4461  jnz     short loc_1400A44D9
0x1400a4463  call    cs:__imp_GetCurrentThreadId
0x1400a446a  nop     dword ptr [rax+rax+00h]
0x1400a446f  mov     qword ptr [rsp+120h+var_E0], r12
0x1400a4474  mov     dword ptr [rsp+120h+var_E8], eax
0x1400a4478  mov     dword ptr [rsp+120h+var_F0], 0D3Ah
0x1400a4480  mov     [rsp+120h+var_F8], r14
0x1400a4485  mov     [rsp+120h+var_100], r15
0x1400a448a  lea     r9d, [rdi+3]
0x1400a448e  xor     r8d, r8d
0x1400a4491  mov     edx, 2336h
0x1400a4496  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a449b  mov     rdi, rax
0x1400a449e  jmp     short loc_1400A44D9
0x1400a44a0  mov     rbx, [rsi+0D8h]
0x1400a44a7  cmp     [rbx+130h], r12
0x1400a44ae  jz      short loc_1400A44C1
0x1400a44b0  mov     rax, [rbx]
0x1400a44b3  mov     rcx, rbx
0x1400a44b6  mov     rax, [rax+10h]
0x1400a44ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a44bf  jmp     short loc_1400A44A7
0x1400a44c1  cmp     [rbx+1C0h], r12
0x1400a44c8  jz      short loc_1400A44D9
0x1400a44ca  xor     edx, edx; int
0x1400a44cc  lea     r8d, [rdx+1]; int
0x1400a44d0  mov     rcx, rbx; this
0x1400a44d3  call    ?CheckPoint@DirWalkerTask@@AEAAPEAVFrsStatus@@HH@Z; DirWalkerTask::CheckPoint(int,int)
0x1400a44d8  nop
0x1400a44d9  lea     rcx, [rbp+3Fh+var_68]
0x1400a44dd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400a44e2  mov     rax, rdi
0x1400a44e5  mov     rcx, [rbp+3Fh+var_48]
0x1400a44e9  xor     rcx, rsp; StackCookie
0x1400a44ec  call    __security_check_cookie
0x1400a44f1  add     rsp, 0E8h
0x1400a44f8  pop     r15
0x1400a44fa  pop     r14
0x1400a44fc  pop     r13
0x1400a44fe  pop     r12
0x1400a4500  pop     rdi
0x1400a4501  pop     rsi
0x1400a4502  pop     rbx
0x1400a4503  pop     rbp
0x1400a4504  retn
```
