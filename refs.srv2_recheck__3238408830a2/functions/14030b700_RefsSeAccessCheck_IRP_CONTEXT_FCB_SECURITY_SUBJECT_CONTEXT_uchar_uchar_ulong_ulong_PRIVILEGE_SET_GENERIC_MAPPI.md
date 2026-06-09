# RefsSeAccessCheck(_IRP_CONTEXT *,_FCB *,_SECURITY_SUBJECT_CONTEXT *,uchar,uchar,ulong,ulong,_PRIVILEGE_SET * *,_GENERIC_MAPPING *,char,ulong *,_ACCESS_REASONS *,long *,_ACCESS_STATE *)

- ea: `0x14030b700`
- end: `0x14030bb3d`
- name: `?RefsSeAccessCheck@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SECURITY_SUBJECT_CONTEXT@@EEKKPEAPEAU_PRIVILEGE_SET@@PEAU_GENERIC_MAPPING@@DPEAKPEAU_ACCESS_REASONS@@PEAJPEAU_ACCESS_STATE@@@Z`
- size: `1085`
- prototype: `unsigned __int8 __fastcall(struct _IRP_CONTEXT *, struct _FCB *, struct _SECURITY_SUBJECT_CONTEXT *, unsigned __int8, char, unsigned int, unsigned int, struct _PRIVILEGE_SET **, struct _GENERIC_MAPPING *, char, unsigned int *, struct _ACCESS_REASONS *, int *, struct _ACCESS_STATE *)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402abb7c`
- `0x1402ac480`
- `0x1402d5f94`
- `0x1402d6250`
- `0x1402d6a88`
- `0x14030a7c0`
- `0x14030bb50`

## callees

- `0x1401f4090`
- `0x14028c008`
- `0x14030b700`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14030b7b5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14030b7b5`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030b7d1`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030bac6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403423c5`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030b7d1`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14030bac6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403423c5`
- `ntoskrnl!SeAccessCheckEx` at `0x14030b992`
- `ntoskrnl!SeAccessCheckEx` at `0x14030b992`
- `ntoskrnl!SeAccessCheckWithHint` at `0x14030baad`
- `ntoskrnl!SeAccessCheckWithHint` at `0x14030baad`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030b7e4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030bad9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403423d8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030b7e4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14030bad9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403423d8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14030b7fa`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14030bb03`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14034240c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14030b7fa`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14030bb03`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14034240c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030b806`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030bb0f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342418`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030b806`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030bb0f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140342418`
- `ntoskrnl!ExReleasePushLockEx` at `0x14030b81b`
- `ntoskrnl!ExReleasePushLockEx` at `0x14030b81b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030baf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403423f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030baf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403423f0`

## pseudocode

```c
__int64 __fastcall RefsSeAccessCheck(
        struct _IRP_CONTEXT *a1,
        struct _FCB *a2,
        struct _SECURITY_SUBJECT_CONTEXT *a3,
        unsigned __int8 a4,
        char a5,
        unsigned int a6,
        unsigned int a7,
        struct _PRIVILEGE_SET **a8,
        struct _GENERIC_MAPPING *a9,
        char a10,
        unsigned int *a11,
        struct _ACCESS_REASONS *a12,
        int *a13,
        struct _ACCESS_STATE *a14)
{
  char v17; // r15
  struct _LIST_ENTRY *Flink; // r14
  PVOID *FileContextSupportPointer; // rbx
  char *v20; // rdi
  __int64 Flink_high; // rdx
  unsigned __int8 v22; // r12
  _QWORD *AuxData; // rbx
  void (*v24)(void); // rax
  void (*v25)(void); // rax
  PVOID *v26; // rbx
  __int128 v29; // [rsp+70h] [rbp-F8h] BYREF
  __int128 v30; // [rsp+80h] [rbp-E8h] BYREF
  __int128 v31; // [rsp+90h] [rbp-D8h]
  struct _PRIVILEGE_SET **v32; // [rsp+A0h] [rbp-C8h]
  __int128 v33; // [rsp+A8h] [rbp-C0h] BYREF
  __int128 v34; // [rsp+B8h] [rbp-B0h]
  __int128 v35; // [rsp+C8h] [rbp-A0h]
  __int64 v36; // [rsp+D8h] [rbp-90h]
  __int128 v37; // [rsp+E0h] [rbp-88h] BYREF
  __int128 v38; // [rsp+F0h] [rbp-78h]
  __int128 v39; // [rsp+100h] [rbp-68h]
  __int128 v40; // [rsp+110h] [rbp-58h]
  __int128 v41; // [rsp+120h] [rbp-48h]
  __int128 v42; // [rsp+130h] [rbp-38h]

  v29 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v17 = 1;
  if ( !a2->ScavengerFinalizationList.Flink )
    RefsLoadSecurityDescriptor(a1, a2);
  ExAcquirePushLockSharedEx(&a2->ScavengerFinalizationList.Blink, 0);
  Flink = a2->ScavengerFinalizationList.Flink;
  FileContextSupportPointer = a2->Header.FileContextSupportPointer;
  KeEnterGuardedRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)FileContextSupportPointer + 13);
  ++LODWORD(Flink->Flink);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)FileContextSupportPointer + 13);
  KeLeaveGuardedRegion();
  ExReleasePushLockEx(&a2->ScavengerFinalizationList.Blink, 0);
  v20 = (char *)&Flink[1].Flink + 4;
  Flink_high = HIDWORD(Flink->Flink);
  if ( a12 )
  {
    LODWORD(v29) = 16;
    *((_QWORD *)&v29 + 1) = (char *)Flink + 20;
    DWORD1(v29) = Flink_high;
    v36 = 0;
    *(_QWORD *)&v33 = 56;
    v34 = __PAIR64__(a7, a6);
    v35 = (unsigned __int64)a9;
    *((_QWORD *)&v33 + 1) = &v29;
    *(_QWORD *)&v30 = 0x100000028LL;
    *((_QWORD *)&v30 + 1) = a11;
    *(_QWORD *)&v31 = a13;
    *((_QWORD *)&v31 + 1) = a12;
    v32 = a8;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    LODWORD(v37) = 96;
    v22 = SeAccessCheckEx(a3, a4, &v33, &v30, &v37, a10);
    if ( a14 )
    {
      AuxData = a14->AuxData;
      if ( a5 )
      {
        if ( AuxData[8] )
        {
          v24 = (void (*)(void))AuxData[9];
          if ( v24 )
          {
            if ( AuxData[10] )
            {
              v24();
              AuxData[8] = 0;
            }
          }
        }
        AuxData[8] = v20;
      }
      else
      {
        if ( AuxData[7] )
        {
          v25 = (void (*)(void))AuxData[9];
          if ( v25 )
          {
            if ( AuxData[10] )
            {
              v25();
              AuxData[7] = 0;
            }
          }
        }
        AuxData[7] = v20;
      }
      v17 = 0;
      *((_QWORD *)a14->AuxData + 9) = RefsDerefExportedSecurityDescriptor;
      *((_QWORD *)a14->AuxData + 10) = a2->Header.FileContextSupportPointer;
      _InterlockedIncrement((volatile signed __int32 *)a2->Header.FileContextSupportPointer + 59);
    }
  }
  else
  {
    v22 = SeAccessCheckWithHint((char *)&Flink[1].Flink + 4, Flink_high, a3, a4, a6, a7, a8, a9, a10, a11, a13);
  }
  if ( v17 )
  {
    v26 = a2->Header.FileContextSupportPointer;
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)v26 + 13);
    if ( LODWORD(Flink->Flink)-- == 1 )
      ExFreePoolWithTag(Flink, 0);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)v26 + 13);
    KeLeaveGuardedRegion();
  }
  return v22;
}

```

## disassembly

```asm
0x14030b700  mov     r11, rsp
0x14030b703  mov     [r11+8], rbx
0x14030b707  mov     [r11+18h], rsi
0x14030b70b  mov     [r11+10h], rdx
0x14030b70f  push    rdi
0x14030b710  push    r12
0x14030b712  push    r13
0x14030b714  push    r14
0x14030b716  push    r15
0x14030b718  sub     rsp, 140h
0x14030b71f  movzx   r12d, r9b
0x14030b723  mov     r13, r8
0x14030b726  mov     rsi, rdx
0x14030b729  mov     [rsp+168h+var_100], 0
0x14030b732  xorps   xmm0, xmm0
0x14030b735  movups  [rsp+168h+var_F8], xmm0
0x14030b73a  xorps   xmm1, xmm1
0x14030b73d  xor     eax, eax
0x14030b73f  movups  [rsp+168h+var_C0], xmm1
0x14030b747  movups  [rsp+168h+var_B0], xmm1
0x14030b74f  movups  [rsp+168h+var_A0], xmm1
0x14030b757  mov     [r11-90h], rax
0x14030b75e  movups  [rsp+168h+var_E8], xmm0
0x14030b766  movups  [rsp+168h+var_D8], xmm0
0x14030b76e  mov     [r11-0C8h], rax
0x14030b775  movups  [rsp+168h+var_88], xmm1
0x14030b77d  movups  xmmword ptr [r11-78h], xmm1
0x14030b782  movups  xmmword ptr [r11-68h], xmm1
0x14030b787  movups  xmmword ptr [r11-58h], xmm1
0x14030b78c  movups  xmmword ptr [r11-48h], xmm1
0x14030b791  movups  xmmword ptr [r11-38h], xmm1
0x14030b796  mov     r15b, 1
0x14030b799  mov     [rsp+168h+var_108], r15b
0x14030b79e  cmp     [rdx+0C0h], rax
0x14030b7a5  jnz     short loc_14030B7AC
0x14030b7a7  call    ?RefsLoadSecurityDescriptor@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsLoadSecurityDescriptor(_IRP_CONTEXT *,_FCB *)
0x14030b7ac  xor     edx, edx
0x14030b7ae  lea     rcx, [rsi+0C8h]
0x14030b7b5  call    cs:__imp_ExAcquirePushLockSharedEx
0x14030b7bc  nop     dword ptr [rax+rax+00h]
0x14030b7c1  mov     r14, [rsi+0C0h]
0x14030b7c8  mov     [rsp+168h+var_100], r14
0x14030b7cd  mov     rbx, [rsi+50h]
0x14030b7d1  call    cs:__imp_KeEnterGuardedRegion
0x14030b7d8  nop     dword ptr [rax+rax+00h]
0x14030b7dd  lea     rcx, [rbx+2D8h]; FastMutex
0x14030b7e4  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14030b7eb  nop     dword ptr [rax+rax+00h]
0x14030b7f0  inc     dword ptr [r14]
0x14030b7f3  lea     rcx, [rbx+2D8h]; FastMutex
0x14030b7fa  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14030b801  nop     dword ptr [rax+rax+00h]
0x14030b806  call    cs:__imp_KeLeaveGuardedRegion
0x14030b80d  nop     dword ptr [rax+rax+00h]
0x14030b812  xor     edx, edx
0x14030b814  lea     rcx, [rsi+0C8h]
0x14030b81b  call    cs:__imp_ExReleasePushLockEx
0x14030b822  nop     dword ptr [rax+rax+00h]
0x14030b827  lea     rdi, [r14+14h]
0x14030b82b  mov     edx, [r14+4]
0x14030b82f  mov     rcx, [rsp+168h+arg_58]
0x14030b837  test    rcx, rcx
0x14030b83a  jz      loc_14030BA4D
0x14030b840  xorps   xmm0, xmm0
0x14030b843  movups  [rsp+168h+var_F8], xmm0
0x14030b848  mov     dword ptr [rsp+168h+var_F8], 10h
0x14030b850  mov     qword ptr [rsp+168h+var_F8+8], rdi
0x14030b855  mov     dword ptr [rsp+168h+var_F8+4], edx
0x14030b859  xor     eax, eax
0x14030b85b  movups  [rsp+168h+var_C0], xmm0
0x14030b863  movups  [rsp+168h+var_B0], xmm0
0x14030b86b  movups  [rsp+168h+var_A0], xmm0
0x14030b873  mov     [rsp+168h+var_90], rax
0x14030b87b  mov     dword ptr [rsp+168h+var_C0], 38h ; '8'
0x14030b886  mov     eax, [rsp+168h+arg_28]
0x14030b88d  mov     dword ptr [rsp+168h+var_B0], eax
0x14030b894  mov     rax, [rsp+168h+arg_40]
0x14030b89c  mov     qword ptr [rsp+168h+var_A0], rax
0x14030b8a4  mov     eax, [rsp+168h+arg_30]
0x14030b8ab  mov     dword ptr [rsp+168h+var_B0+4], eax
0x14030b8b2  lea     rax, [rsp+168h+var_F8]
0x14030b8b7  mov     qword ptr [rsp+168h+var_C0+8], rax
0x14030b8bf  xor     eax, eax
0x14030b8c1  movups  [rsp+168h+var_E8], xmm0
0x14030b8c9  movups  [rsp+168h+var_D8], xmm0
0x14030b8d1  mov     [rsp+168h+var_C8], rax
0x14030b8d9  mov     dword ptr [rsp+168h+var_E8], 28h ; '('
0x14030b8e4  mov     dword ptr [rsp+168h+var_E8+4], 1
0x14030b8ef  mov     rax, [rsp+168h+arg_50]
0x14030b8f7  mov     qword ptr [rsp+168h+var_E8+8], rax
0x14030b8ff  mov     rax, [rsp+168h+arg_60]
0x14030b907  mov     qword ptr [rsp+168h+var_D8], rax
0x14030b90f  mov     qword ptr [rsp+168h+var_D8+8], rcx
0x14030b917  mov     rax, [rsp+168h+arg_38]
0x14030b91f  mov     [rsp+168h+var_C8], rax
0x14030b927  movups  [rsp+168h+var_88], xmm0
0x14030b92f  movups  [rsp+168h+var_78], xmm0
0x14030b937  movups  [rsp+168h+var_68], xmm0
0x14030b93f  movups  [rsp+168h+var_58], xmm0
0x14030b947  movups  [rsp+168h+var_48], xmm0
0x14030b94f  movups  [rsp+168h+var_38], xmm0
0x14030b957  mov     dword ptr [rsp+168h+var_88], 60h ; '`'
0x14030b962  movzx   eax, [rsp+168h+arg_48]
0x14030b96a  mov     byte ptr [rsp+168h+var_140], al
0x14030b96e  lea     rax, [rsp+168h+var_88]
0x14030b976  mov     [rsp+168h+var_148], rax
0x14030b97b  lea     r9, [rsp+168h+var_E8]
0x14030b983  lea     r8, [rsp+168h+var_C0]
0x14030b98b  movzx   edx, r12b
0x14030b98f  mov     rcx, r13
0x14030b992  call    cs:__imp_SeAccessCheckEx
0x14030b999  nop     dword ptr [rax+rax+00h]
0x14030b99e  movzx   r12d, al
0x14030b9a2  mov     r13, [rsp+168h+arg_68]
0x14030b9aa  test    r13, r13
0x14030b9ad  jz      loc_14030BABD
0x14030b9b3  mov     rbx, [r13+48h]
0x14030b9b7  cmp     [rsp+168h+arg_20], 0
0x14030b9bf  jz      short loc_14030B9EF
0x14030b9c1  mov     rdx, [rbx+40h]
0x14030b9c5  test    rdx, rdx
0x14030b9c8  jz      short loc_14030B9E9
0x14030b9ca  mov     rax, [rbx+48h]
0x14030b9ce  test    rax, rax
0x14030b9d1  jz      short loc_14030B9E9
0x14030b9d3  mov     rcx, [rbx+50h]
0x14030b9d7  test    rcx, rcx
0x14030b9da  jz      short loc_14030B9E9
0x14030b9dc  call    _guard_dispatch_icall
0x14030b9e1  mov     qword ptr [rbx+40h], 0
0x14030b9e9  mov     [rbx+40h], rdi
0x14030b9ed  jmp     short loc_14030BA1B
0x14030b9ef  mov     rdx, [rbx+38h]
0x14030b9f3  test    rdx, rdx
0x14030b9f6  jz      short loc_14030BA17
0x14030b9f8  mov     rax, [rbx+48h]
0x14030b9fc  test    rax, rax
0x14030b9ff  jz      short loc_14030BA17
0x14030ba01  mov     rcx, [rbx+50h]
0x14030ba05  test    rcx, rcx
0x14030ba08  jz      short loc_14030BA17
0x14030ba0a  call    _guard_dispatch_icall
0x14030ba0f  mov     qword ptr [rbx+38h], 0
0x14030ba17  mov     [rbx+38h], rdi
0x14030ba1b  xor     r15b, r15b
0x14030ba1e  mov     [rsp+168h+var_108], r15b
0x14030ba23  mov     rax, [r13+48h]
0x14030ba27  lea     rcx, ?RefsDerefExportedSecurityDescriptor@@YAXPEAX0@Z; RefsDerefExportedSecurityDescriptor(void *,void *)
0x14030ba2e  mov     [rax+48h], rcx
0x14030ba32  mov     rcx, [r13+48h]
0x14030ba36  mov     rax, [rsi+50h]
0x14030ba3a  mov     [rcx+50h], rax
0x14030ba3e  mov     rax, [rsi+50h]
0x14030ba42  add     rax, 0ECh
0x14030ba48  lock inc dword ptr [rax]
0x14030ba4b  jmp     short loc_14030BABD
0x14030ba4d  mov     rax, [rsp+168h+arg_60]
0x14030ba55  mov     [rsp+168h+var_118], rax
0x14030ba5a  mov     rax, [rsp+168h+arg_50]
0x14030ba62  mov     [rsp+168h+var_120], rax
0x14030ba67  movzx   eax, [rsp+168h+arg_48]
0x14030ba6f  mov     [rsp+168h+var_128], al
0x14030ba73  mov     rax, [rsp+168h+arg_40]
0x14030ba7b  mov     [rsp+168h+var_130], rax
0x14030ba80  mov     rax, [rsp+168h+arg_38]
0x14030ba88  mov     [rsp+168h+var_138], rax
0x14030ba8d  mov     eax, [rsp+168h+arg_30]
0x14030ba94  mov     [rsp+168h+var_140], eax
0x14030ba98  mov     eax, [rsp+168h+arg_28]
0x14030ba9f  mov     dword ptr [rsp+168h+var_148], eax
0x14030baa3  movzx   r9d, r12b
0x14030baa7  mov     r8, r13
0x14030baaa  mov     rcx, rdi
0x14030baad  call    cs:__imp_SeAccessCheckWithHint
0x14030bab4  nop     dword ptr [rax+rax+00h]
0x14030bab9  movzx   r12d, al
0x14030babd  test    r15b, r15b
0x14030bac0  jz      short loc_14030BB1B
0x14030bac2  mov     rbx, [rsi+50h]
0x14030bac6  call    cs:__imp_KeEnterGuardedRegion
0x14030bacd  nop     dword ptr [rax+rax+00h]
0x14030bad2  lea     rcx, [rbx+2D8h]; FastMutex
0x14030bad9  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14030bae0  nop     dword ptr [rax+rax+00h]
0x14030bae5  add     dword ptr [r14], 0FFFFFFFFh
0x14030bae9  jnz     short loc_14030BAFC
0x14030baeb  xor     edx, edx; Tag
0x14030baed  mov     rcx, r14; P
0x14030baf0  call    cs:__imp_ExFreePoolWithTag
0x14030baf7  nop     dword ptr [rax+rax+00h]
0x14030bafc  lea     rcx, [rbx+2D8h]; FastMutex
0x14030bb03  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14030bb0a  nop     dword ptr [rax+rax+00h]
0x14030bb0f  call    cs:__imp_KeLeaveGuardedRegion
0x14030bb16  nop     dword ptr [rax+rax+00h]
0x14030bb1b  movzx   eax, r12b
0x14030bb1f  lea     r11, [rsp+168h+var_28]
0x14030bb27  mov     rbx, [r11+30h]
0x14030bb2b  mov     rsi, [r11+40h]
0x14030bb2f  mov     rsp, r11
0x14030bb32  pop     r15
0x14030bb34  pop     r14
0x14030bb36  pop     r13
0x14030bb38  pop     r12
0x14030bb3a  pop     rdi
0x14030bb3b  retn
0x1403423a0  push    rbx
0x1403423a2  push    rbp
0x1403423a3  push    rdi
0x1403423a4  sub     rsp, 60h
0x1403423a8  mov     rbp, rdx
0x1403423ab  cmp     byte ptr [rbp+60h], 0
0x1403423af  jz      short loc_140342425
0x1403423b1  mov     rbx, [rbp+68h]
0x1403423b5  test    rbx, rbx
0x1403423b8  jz      short loc_140342425
0x1403423ba  mov     rax, [rbp+178h]
0x1403423c1  mov     rdi, [rax+50h]
0x1403423c5  call    cs:__imp_KeEnterGuardedRegion
0x1403423cc  nop     dword ptr [rax+rax+00h]
0x1403423d1  lea     rcx, [rdi+2D8h]; FastMutex
0x1403423d8  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1403423df  nop     dword ptr [rax+rax+00h]
0x1403423e4  add     dword ptr [rbx], 0FFFFFFFFh
0x1403423e7  mov     eax, [rbx]
0x1403423e9  jnz     short loc_1403423FD
0x1403423eb  xor     edx, edx; Tag
0x1403423ed  mov     rcx, rbx; P
0x1403423f0  call    cs:__imp_ExFreePoolWithTag
0x1403423f7  nop     dword ptr [rax+rax+00h]
0x1403423fc  nop
0x1403423fd  mov     qword ptr [rbp+68h], 0
0x140342405  lea     rcx, [rdi+2D8h]; FastMutex
0x14034240c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140342413  nop     dword ptr [rax+rax+00h]
0x140342418  call    cs:__imp_KeLeaveGuardedRegion
0x14034241f  nop     dword ptr [rax+rax+00h]
0x140342424  nop
0x140342425  add     rsp, 60h
0x140342429  pop     rdi
0x14034242a  pop     rbp
0x14034242b  pop     rbx
0x14034242c  retn
```
