# FIEnumerate

- ea: `0x140013d70`
- end: `0x140013fa7`
- name: `FIEnumerate`
- size: `567`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140012e50`
- `0x140013050`

## callees

- `0x140001c00`
- `0x140001da0`
- `0x140001f20`
- `0x140013d70`
- `0x140013fb0`
- `0x1400145b8`
- `0x140014648`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140013e4a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140013e4a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140013e67`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140013e67`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013f38`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013f38`
- `FLTMGR!FltReferenceFileNameInformation` at `0x140013ebf`
- `FLTMGR!FltReferenceFileNameInformation` at `0x140013ebf`

## pseudocode

```c
__int64 __fastcall FIEnumerate(__int64 a1)
{
  struct _EX_RUNDOWN_REF *v2; // rbx
  __int64 i; // r12
  unsigned int v4; // ecx
  int v5; // eax
  struct _EX_RUNDOWN_REF **v6; // r15
  struct _EX_RUNDOWN_REF *Count; // rdi
  BOOLEAN j; // si
  unsigned int v9; // ecx
  int v10; // eax
  PFLT_FILE_NAME_INFORMATION FileNameInformation[2]; // [rsp+20h] [rbp-39h] BYREF
  ULONG_PTR v13; // [rsp+30h] [rbp-29h]
  _DWORD v14[2]; // [rsp+38h] [rbp-21h] BYREF
  __int64 v15; // [rsp+40h] [rbp-19h]
  __int64 v16; // [rsp+48h] [rbp-11h]
  int v17; // [rsp+50h] [rbp-9h]
  int v18; // [rsp+54h] [rbp-5h]
  __int64 v19; // [rsp+58h] [rbp-1h]
  __int128 v20; // [rsp+60h] [rbp+7h] BYREF
  __int128 v21; // [rsp+70h] [rbp+17h]
  __int128 v22; // [rsp+80h] [rbp+27h]

  v18 = 0;
  v13 = 0;
  v20 = 0;
  v2 = 0;
  v21 = 0;
  v22 = 0;
  *(_OWORD *)FileNameInformation = 0;
  for ( i = FIVolumeGetNext(0); i; i = FIVolumeGetNext(i) )
  {
    v4 = *(_DWORD *)(a1 + 4);
    v16 = i;
    v17 = 5;
    v19 = 0;
    v15 = *(_QWORD *)(a1 + 16);
    v5 = *(_DWORD *)(a1 + 8);
    v14[0] = dword_140009A74 & 0xFFFFFFFC | (2 * (v4 & 1)) | (v4 >> 1) & 1;
    v14[1] = v5;
    FIVolumeLog(v14);
    v6 = (struct _EX_RUNDOWN_REF **)(i + 32);
    while ( 1 )
    {
      FILockExclusiveAcquire(i + 24);
      if ( v2 )
      {
        Count = (struct _EX_RUNDOWN_REF *)v2->Count;
        ExReleaseRundownProtection(v2 + 2);
      }
      else
      {
        Count = *v6;
      }
      v2 = 0;
      for ( j = 0; Count != (struct _EX_RUNDOWN_REF *)v6; Count = (struct _EX_RUNDOWN_REF *)Count->Count )
      {
        v2 = Count;
        j = ExAcquireRundownProtection(Count + 2);
        if ( j )
          break;
      }
      FILockExclusiveRelease(i + 24);
      if ( !j )
        v2 = 0;
      if ( !v2 )
        break;
      FILockSharedAcquire((__int64)&v2[5]);
      *(_OWORD *)FileNameInformation = *(_OWORD *)&v2[6].Count;
      v13 = v2[8].Count;
      if ( FileNameInformation[0] )
        FltReferenceFileNameInformation(FileNameInformation[0]);
      LODWORD(FileNameInformation[1]) &= ~0x40u;
      FILockExclusiveRelease((__int64)&v2[5]);
      *(_QWORD *)&v21 = v2;
      v22 = (unsigned __int64)FileNameInformation;
      v9 = *(_DWORD *)(a1 + 4);
      DWORD2(v21) = 6;
      *((_QWORD *)&v20 + 1) = *(_QWORD *)(a1 + 16);
      v10 = *(_DWORD *)(a1 + 8);
      LODWORD(v20) = dword_140009A74 & 0xFFFFFFFC | (2 * (v9 & 1)) | (v9 >> 1) & 1;
      DWORD1(v20) = v10;
      FIStreamLog((__int64)&v20);
      if ( FileNameInformation[0] )
        FltReleaseFileNameInformation(FileNameInformation[0]);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140013d70  push    rbp
0x140013d72  push    rbx
0x140013d73  push    r12
0x140013d75  push    r13
0x140013d77  lea     rbp, [rsp-3Fh]
0x140013d7c  sub     rsp, 98h
0x140013d83  xorps   xmm0, xmm0
0x140013d86  mov     [rbp+57h+var_5C], 0
0x140013d8d  mov     r13, rcx
0x140013d90  xor     eax, eax
0x140013d92  xor     ecx, ecx
0x140013d94  mov     [rbp+57h+var_80], rax
0x140013d98  movups  [rbp+57h+var_50], xmm0
0x140013d9c  xor     ebx, ebx
0x140013d9e  movups  [rbp+57h+var_40], xmm0
0x140013da2  movups  [rbp+57h+var_30], xmm0
0x140013da6  movups  xmmword ptr [rbp+57h+FileNameInformation], xmm0
0x140013daa  call    FIVolumeGetNext
0x140013daf  mov     r12, rax
0x140013db2  test    rax, rax
0x140013db5  jz      loc_140013F7D
0x140013dbb  mov     [rsp+0B0h+arg_0], rsi
0x140013dc3  mov     [rsp+0B0h+arg_8], rdi
0x140013dcb  mov     [rsp+0B0h+arg_10], r14
0x140013dd3  mov     [rsp+0B0h+var_20], r15
0x140013ddb  mov     eax, [r13+4]
0x140013ddf  mov     ecx, eax
0x140013de1  and     eax, 1
0x140013de4  shr     ecx, 1
0x140013de6  add     eax, eax
0x140013de8  mov     [rbp+57h+var_68], r12
0x140013dec  and     ecx, 1
0x140013def  mov     [rbp+57h+var_60], 5
0x140013df6  or      ecx, eax
0x140013df8  mov     [rbp+57h+var_58], 0
0x140013e00  mov     eax, cs:dword_140009A74
0x140013e06  and     eax, 0FFFFFFFCh
0x140013e09  or      ecx, eax
0x140013e0b  mov     rax, [r13+10h]
0x140013e0f  mov     [rbp+57h+var_70], rax
0x140013e13  mov     eax, [r13+8]
0x140013e17  mov     [rbp+57h+var_78], ecx
0x140013e1a  lea     rcx, [rbp+57h+var_78]
0x140013e1e  mov     [rbp+57h+var_74], eax
0x140013e21  call    FIVolumeLog
0x140013e26  lea     r15, [r12+20h]
0x140013e2b  nop     dword ptr [rax+rax+00h]
0x140013e30  lea     rcx, [r12+18h]
0x140013e35  call    FILockExclusiveAcquire
0x140013e3a  test    rbx, rbx
0x140013e3d  jz      loc_140013F8E
0x140013e43  mov     rdi, [rbx]
0x140013e46  lea     rcx, [rbx+10h]; RunRef
0x140013e4a  call    cs:__imp_ExReleaseRundownProtection
0x140013e51  nop     dword ptr [rax+rax+00h]
0x140013e56  xor     ebx, ebx
0x140013e58  xor     sil, sil
0x140013e5b  cmp     rdi, r15
0x140013e5e  jz      short loc_140013E7E
0x140013e60  lea     rcx, [rdi+10h]; RunRef
0x140013e64  mov     rbx, rdi
0x140013e67  call    cs:__imp_ExAcquireRundownProtection
0x140013e6e  nop     dword ptr [rax+rax+00h]
0x140013e73  movzx   esi, al
0x140013e76  test    al, al
0x140013e78  jz      loc_140013F96
0x140013e7e  lea     rcx, [r12+18h]
0x140013e83  call    FILockExclusiveRelease
0x140013e88  xor     ecx, ecx
0x140013e8a  test    sil, sil
0x140013e8d  cmovz   rbx, rcx
0x140013e91  test    rbx, rbx
0x140013e94  jz      loc_140013F49
0x140013e9a  lea     rcx, [rbx+28h]
0x140013e9e  call    FILockSharedAcquire
0x140013ea3  movups  xmm1, xmmword ptr [rbx+30h]
0x140013ea7  movups  xmmword ptr [rbp+57h+FileNameInformation], xmm1
0x140013eab  movsd   xmm0, qword ptr [rbx+40h]
0x140013eb0  movq    rcx, xmm1; FileNameInformation
0x140013eb5  movsd   [rbp+57h+var_80], xmm0
0x140013eba  test    rcx, rcx
0x140013ebd  jz      short loc_140013ECB
0x140013ebf  call    cs:__imp_FltReferenceFileNameInformation
0x140013ec6  nop     dword ptr [rax+rax+00h]
0x140013ecb  and     dword ptr [rbp+57h+FileNameInformation+8], 0FFFFFFBFh
0x140013ecf  lea     rcx, [rbx+28h]
0x140013ed3  call    FILockExclusiveRelease
0x140013ed8  lea     rax, [rbp+57h+FileNameInformation]
0x140013edc  mov     qword ptr [rbp+57h+var_40], rbx
0x140013ee0  mov     qword ptr [rbp+57h+var_30], rax
0x140013ee4  mov     eax, [r13+4]
0x140013ee8  mov     ecx, eax
0x140013eea  and     eax, 1
0x140013eed  shr     ecx, 1
0x140013eef  add     eax, eax
0x140013ef1  mov     dword ptr [rbp+57h+var_40+8], 6
0x140013ef8  and     ecx, 1
0x140013efb  mov     qword ptr [rbp+57h+var_30+8], 0
0x140013f03  or      ecx, eax
0x140013f05  mov     eax, cs:dword_140009A74
0x140013f0b  and     eax, 0FFFFFFFCh
0x140013f0e  or      ecx, eax
0x140013f10  mov     rax, [r13+10h]
0x140013f14  mov     qword ptr [rbp+57h+var_50+8], rax
0x140013f18  mov     eax, [r13+8]
0x140013f1c  mov     dword ptr [rbp+57h+var_50], ecx
0x140013f1f  lea     rcx, [rbp+57h+var_50]
0x140013f23  mov     dword ptr [rbp+57h+var_50+4], eax
0x140013f26  call    FIStreamLog
0x140013f2b  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140013f2f  test    rcx, rcx
0x140013f32  jz      loc_140013E30
0x140013f38  call    cs:__imp_FltReleaseFileNameInformation
0x140013f3f  nop     dword ptr [rax+rax+00h]
0x140013f44  jmp     loc_140013E30
0x140013f49  mov     rcx, r12
0x140013f4c  call    FIVolumeGetNext
0x140013f51  mov     r12, rax
0x140013f54  test    rax, rax
0x140013f57  jnz     loc_140013DDB
0x140013f5d  mov     r15, [rsp+0B0h+var_20]
0x140013f65  mov     r14, [rsp+0B0h+arg_10]
0x140013f6d  mov     rdi, [rsp+0B0h+arg_8]
0x140013f75  mov     rsi, [rsp+0B0h+arg_0]
0x140013f7d  xor     eax, eax
0x140013f7f  add     rsp, 98h
0x140013f86  pop     r13
0x140013f88  pop     r12
0x140013f8a  pop     rbx
0x140013f8b  pop     rbp
0x140013f8c  retn
0x140013f8e  mov     rdi, [r15]
0x140013f91  jmp     loc_140013E56
0x140013f96  mov     rdi, [rdi]
0x140013f99  cmp     rdi, r15
0x140013f9c  jnz     loc_140013E60
0x140013fa2  jmp     loc_140013E7E
```
