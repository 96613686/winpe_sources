# RefsSeAccessCheck(_IRP_CONTEXT *,_FCB *,_SECURITY_SUBJECT_CONTEXT *,uchar,uchar,ulong,ulong,_PRIVILEGE_SET * *,_GENERIC_MAPPING *,char,ulong *,_ACCESS_REASONS *,long *,_ACCESS_STATE *)

- ea: `0x140308080`
- end: `0x1403084bd`
- name: `?RefsSeAccessCheck@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SECURITY_SUBJECT_CONTEXT@@EEKKPEAPEAU_PRIVILEGE_SET@@PEAU_GENERIC_MAPPING@@DPEAKPEAU_ACCESS_REASONS@@PEAJPEAU_ACCESS_STATE@@@Z`
- size: `1085`
- prototype: `unsigned __int8 __fastcall(struct _IRP_CONTEXT *, struct _FCB *, struct _SECURITY_SUBJECT_CONTEXT *, unsigned __int8, char, unsigned int, unsigned int, struct _PRIVILEGE_SET **, struct _GENERIC_MAPPING *, char, unsigned int *, struct _ACCESS_REASONS *, int *, struct _ACCESS_STATE *)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402a4e1c`
- `0x1402a5720`
- `0x1402d1054`
- `0x1402d1310`
- `0x1402d1b48`
- `0x140307140`
- `0x1403084d0`

## callees

- `0x1401e9dc0`
- `0x140285008`
- `0x140308080`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140308135`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140308135`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140308151`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140308446`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033f4f5`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140308151`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140308446`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033f4f5`
- `ntoskrnl!SeAccessCheckEx` at `0x140308312`
- `ntoskrnl!SeAccessCheckEx` at `0x140308312`
- `ntoskrnl!SeAccessCheckWithHint` at `0x14030842d`
- `ntoskrnl!SeAccessCheckWithHint` at `0x14030842d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140308164`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140308459`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033f508`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140308164`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140308459`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033f508`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14030817a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140308483`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033f53c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14030817a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140308483`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033f53c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140308186`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030848f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033f548`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140308186`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14030848f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033f548`
- `ntoskrnl!ExReleasePushLockEx` at `0x14030819b`
- `ntoskrnl!ExReleasePushLockEx` at `0x14030819b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140308470`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f520`
- `ntoskrnl!ExFreePoolWithTag` at `0x140308470`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f520`

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
0x140308080  mov     r11, rsp
0x140308083  mov     [r11+8], rbx
0x140308087  mov     [r11+18h], rsi
0x14030808b  mov     [r11+10h], rdx
0x14030808f  push    rdi
0x140308090  push    r12
0x140308092  push    r13
0x140308094  push    r14
0x140308096  push    r15
0x140308098  sub     rsp, 140h
0x14030809f  movzx   r12d, r9b
0x1403080a3  mov     r13, r8
0x1403080a6  mov     rsi, rdx
0x1403080a9  mov     [rsp+168h+var_100], 0
0x1403080b2  xorps   xmm0, xmm0
0x1403080b5  movups  [rsp+168h+var_F8], xmm0
0x1403080ba  xorps   xmm1, xmm1
0x1403080bd  xor     eax, eax
0x1403080bf  movups  [rsp+168h+var_C0], xmm1
0x1403080c7  movups  [rsp+168h+var_B0], xmm1
0x1403080cf  movups  [rsp+168h+var_A0], xmm1
0x1403080d7  mov     [r11-90h], rax
0x1403080de  movups  [rsp+168h+var_E8], xmm0
0x1403080e6  movups  [rsp+168h+var_D8], xmm0
0x1403080ee  mov     [r11-0C8h], rax
0x1403080f5  movups  [rsp+168h+var_88], xmm1
0x1403080fd  movups  xmmword ptr [r11-78h], xmm1
0x140308102  movups  xmmword ptr [r11-68h], xmm1
0x140308107  movups  xmmword ptr [r11-58h], xmm1
0x14030810c  movups  xmmword ptr [r11-48h], xmm1
0x140308111  movups  xmmword ptr [r11-38h], xmm1
0x140308116  mov     r15b, 1
0x140308119  mov     [rsp+168h+var_108], r15b
0x14030811e  cmp     [rdx+0C0h], rax
0x140308125  jnz     short loc_14030812C
0x140308127  call    ?RefsLoadSecurityDescriptor@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsLoadSecurityDescriptor(_IRP_CONTEXT *,_FCB *)
0x14030812c  xor     edx, edx
0x14030812e  lea     rcx, [rsi+0C8h]
0x140308135  call    cs:__imp_ExAcquirePushLockSharedEx
0x14030813c  nop     dword ptr [rax+rax+00h]
0x140308141  mov     r14, [rsi+0C0h]
0x140308148  mov     [rsp+168h+var_100], r14
0x14030814d  mov     rbx, [rsi+50h]
0x140308151  call    cs:__imp_KeEnterGuardedRegion
0x140308158  nop     dword ptr [rax+rax+00h]
0x14030815d  lea     rcx, [rbx+2D8h]; FastMutex
0x140308164  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14030816b  nop     dword ptr [rax+rax+00h]
0x140308170  inc     dword ptr [r14]
0x140308173  lea     rcx, [rbx+2D8h]; FastMutex
0x14030817a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140308181  nop     dword ptr [rax+rax+00h]
0x140308186  call    cs:__imp_KeLeaveGuardedRegion
0x14030818d  nop     dword ptr [rax+rax+00h]
0x140308192  xor     edx, edx
0x140308194  lea     rcx, [rsi+0C8h]
0x14030819b  call    cs:__imp_ExReleasePushLockEx
0x1403081a2  nop     dword ptr [rax+rax+00h]
0x1403081a7  lea     rdi, [r14+14h]
0x1403081ab  mov     edx, [r14+4]
0x1403081af  mov     rcx, [rsp+168h+arg_58]
0x1403081b7  test    rcx, rcx
0x1403081ba  jz      loc_1403083CD
0x1403081c0  xorps   xmm0, xmm0
0x1403081c3  movups  [rsp+168h+var_F8], xmm0
0x1403081c8  mov     dword ptr [rsp+168h+var_F8], 10h
0x1403081d0  mov     qword ptr [rsp+168h+var_F8+8], rdi
0x1403081d5  mov     dword ptr [rsp+168h+var_F8+4], edx
0x1403081d9  xor     eax, eax
0x1403081db  movups  [rsp+168h+var_C0], xmm0
0x1403081e3  movups  [rsp+168h+var_B0], xmm0
0x1403081eb  movups  [rsp+168h+var_A0], xmm0
0x1403081f3  mov     [rsp+168h+var_90], rax
0x1403081fb  mov     dword ptr [rsp+168h+var_C0], 38h ; '8'
0x140308206  mov     eax, [rsp+168h+arg_28]
0x14030820d  mov     dword ptr [rsp+168h+var_B0], eax
0x140308214  mov     rax, [rsp+168h+arg_40]
0x14030821c  mov     qword ptr [rsp+168h+var_A0], rax
0x140308224  mov     eax, [rsp+168h+arg_30]
0x14030822b  mov     dword ptr [rsp+168h+var_B0+4], eax
0x140308232  lea     rax, [rsp+168h+var_F8]
0x140308237  mov     qword ptr [rsp+168h+var_C0+8], rax
0x14030823f  xor     eax, eax
0x140308241  movups  [rsp+168h+var_E8], xmm0
0x140308249  movups  [rsp+168h+var_D8], xmm0
0x140308251  mov     [rsp+168h+var_C8], rax
0x140308259  mov     dword ptr [rsp+168h+var_E8], 28h ; '('
0x140308264  mov     dword ptr [rsp+168h+var_E8+4], 1
0x14030826f  mov     rax, [rsp+168h+arg_50]
0x140308277  mov     qword ptr [rsp+168h+var_E8+8], rax
0x14030827f  mov     rax, [rsp+168h+arg_60]
0x140308287  mov     qword ptr [rsp+168h+var_D8], rax
0x14030828f  mov     qword ptr [rsp+168h+var_D8+8], rcx
0x140308297  mov     rax, [rsp+168h+arg_38]
0x14030829f  mov     [rsp+168h+var_C8], rax
0x1403082a7  movups  [rsp+168h+var_88], xmm0
0x1403082af  movups  [rsp+168h+var_78], xmm0
0x1403082b7  movups  [rsp+168h+var_68], xmm0
0x1403082bf  movups  [rsp+168h+var_58], xmm0
0x1403082c7  movups  [rsp+168h+var_48], xmm0
0x1403082cf  movups  [rsp+168h+var_38], xmm0
0x1403082d7  mov     dword ptr [rsp+168h+var_88], 60h ; '`'
0x1403082e2  movzx   eax, [rsp+168h+arg_48]
0x1403082ea  mov     byte ptr [rsp+168h+var_140], al
0x1403082ee  lea     rax, [rsp+168h+var_88]
0x1403082f6  mov     [rsp+168h+var_148], rax
0x1403082fb  lea     r9, [rsp+168h+var_E8]
0x140308303  lea     r8, [rsp+168h+var_C0]
0x14030830b  movzx   edx, r12b
0x14030830f  mov     rcx, r13
0x140308312  call    cs:__imp_SeAccessCheckEx
0x140308319  nop     dword ptr [rax+rax+00h]
0x14030831e  movzx   r12d, al
0x140308322  mov     r13, [rsp+168h+arg_68]
0x14030832a  test    r13, r13
0x14030832d  jz      loc_14030843D
0x140308333  mov     rbx, [r13+48h]
0x140308337  cmp     [rsp+168h+arg_20], 0
0x14030833f  jz      short loc_14030836F
0x140308341  mov     rdx, [rbx+40h]
0x140308345  test    rdx, rdx
0x140308348  jz      short loc_140308369
0x14030834a  mov     rax, [rbx+48h]
0x14030834e  test    rax, rax
0x140308351  jz      short loc_140308369
0x140308353  mov     rcx, [rbx+50h]
0x140308357  test    rcx, rcx
0x14030835a  jz      short loc_140308369
0x14030835c  call    _guard_dispatch_icall
0x140308361  mov     qword ptr [rbx+40h], 0
0x140308369  mov     [rbx+40h], rdi
0x14030836d  jmp     short loc_14030839B
0x14030836f  mov     rdx, [rbx+38h]
0x140308373  test    rdx, rdx
0x140308376  jz      short loc_140308397
0x140308378  mov     rax, [rbx+48h]
0x14030837c  test    rax, rax
0x14030837f  jz      short loc_140308397
0x140308381  mov     rcx, [rbx+50h]
0x140308385  test    rcx, rcx
0x140308388  jz      short loc_140308397
0x14030838a  call    _guard_dispatch_icall
0x14030838f  mov     qword ptr [rbx+38h], 0
0x140308397  mov     [rbx+38h], rdi
0x14030839b  xor     r15b, r15b
0x14030839e  mov     [rsp+168h+var_108], r15b
0x1403083a3  mov     rax, [r13+48h]
0x1403083a7  lea     rcx, ?RefsDerefExportedSecurityDescriptor@@YAXPEAX0@Z; RefsDerefExportedSecurityDescriptor(void *,void *)
0x1403083ae  mov     [rax+48h], rcx
0x1403083b2  mov     rcx, [r13+48h]
0x1403083b6  mov     rax, [rsi+50h]
0x1403083ba  mov     [rcx+50h], rax
0x1403083be  mov     rax, [rsi+50h]
0x1403083c2  add     rax, 0ECh
0x1403083c8  lock inc dword ptr [rax]
0x1403083cb  jmp     short loc_14030843D
0x1403083cd  mov     rax, [rsp+168h+arg_60]
0x1403083d5  mov     [rsp+168h+var_118], rax
0x1403083da  mov     rax, [rsp+168h+arg_50]
0x1403083e2  mov     [rsp+168h+var_120], rax
0x1403083e7  movzx   eax, [rsp+168h+arg_48]
0x1403083ef  mov     [rsp+168h+var_128], al
0x1403083f3  mov     rax, [rsp+168h+arg_40]
0x1403083fb  mov     [rsp+168h+var_130], rax
0x140308400  mov     rax, [rsp+168h+arg_38]
0x140308408  mov     [rsp+168h+var_138], rax
0x14030840d  mov     eax, [rsp+168h+arg_30]
0x140308414  mov     [rsp+168h+var_140], eax
0x140308418  mov     eax, [rsp+168h+arg_28]
0x14030841f  mov     dword ptr [rsp+168h+var_148], eax
0x140308423  movzx   r9d, r12b
0x140308427  mov     r8, r13
0x14030842a  mov     rcx, rdi
0x14030842d  call    cs:__imp_SeAccessCheckWithHint
0x140308434  nop     dword ptr [rax+rax+00h]
0x140308439  movzx   r12d, al
0x14030843d  test    r15b, r15b
0x140308440  jz      short loc_14030849B
0x140308442  mov     rbx, [rsi+50h]
0x140308446  call    cs:__imp_KeEnterGuardedRegion
0x14030844d  nop     dword ptr [rax+rax+00h]
0x140308452  lea     rcx, [rbx+2D8h]; FastMutex
0x140308459  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140308460  nop     dword ptr [rax+rax+00h]
0x140308465  add     dword ptr [r14], 0FFFFFFFFh
0x140308469  jnz     short loc_14030847C
0x14030846b  xor     edx, edx; Tag
0x14030846d  mov     rcx, r14; P
0x140308470  call    cs:__imp_ExFreePoolWithTag
0x140308477  nop     dword ptr [rax+rax+00h]
0x14030847c  lea     rcx, [rbx+2D8h]; FastMutex
0x140308483  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14030848a  nop     dword ptr [rax+rax+00h]
0x14030848f  call    cs:__imp_KeLeaveGuardedRegion
0x140308496  nop     dword ptr [rax+rax+00h]
0x14030849b  movzx   eax, r12b
0x14030849f  lea     r11, [rsp+168h+var_28]
0x1403084a7  mov     rbx, [r11+30h]
0x1403084ab  mov     rsi, [r11+40h]
0x1403084af  mov     rsp, r11
0x1403084b2  pop     r15
0x1403084b4  pop     r14
0x1403084b6  pop     r13
0x1403084b8  pop     r12
0x1403084ba  pop     rdi
0x1403084bb  retn
0x14033f4d0  push    rbx
0x14033f4d2  push    rbp
0x14033f4d3  push    rdi
0x14033f4d4  sub     rsp, 60h
0x14033f4d8  mov     rbp, rdx
0x14033f4db  cmp     byte ptr [rbp+60h], 0
0x14033f4df  jz      short loc_14033F555
0x14033f4e1  mov     rbx, [rbp+68h]
0x14033f4e5  test    rbx, rbx
0x14033f4e8  jz      short loc_14033F555
0x14033f4ea  mov     rax, [rbp+178h]
0x14033f4f1  mov     rdi, [rax+50h]
0x14033f4f5  call    cs:__imp_KeEnterGuardedRegion
0x14033f4fc  nop     dword ptr [rax+rax+00h]
0x14033f501  lea     rcx, [rdi+2D8h]; FastMutex
0x14033f508  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14033f50f  nop     dword ptr [rax+rax+00h]
0x14033f514  add     dword ptr [rbx], 0FFFFFFFFh
0x14033f517  mov     eax, [rbx]
0x14033f519  jnz     short loc_14033F52D
0x14033f51b  xor     edx, edx; Tag
0x14033f51d  mov     rcx, rbx; P
0x14033f520  call    cs:__imp_ExFreePoolWithTag
0x14033f527  nop     dword ptr [rax+rax+00h]
0x14033f52c  nop
0x14033f52d  mov     qword ptr [rbp+68h], 0
0x14033f535  lea     rcx, [rdi+2D8h]; FastMutex
0x14033f53c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14033f543  nop     dword ptr [rax+rax+00h]
0x14033f548  call    cs:__imp_KeLeaveGuardedRegion
0x14033f54f  nop     dword ptr [rax+rax+00h]
0x14033f554  nop
0x14033f555  add     rsp, 60h
0x14033f559  pop     rdi
0x14033f55a  pop     rbp
0x14033f55b  pop     rbx
0x14033f55c  retn
```
