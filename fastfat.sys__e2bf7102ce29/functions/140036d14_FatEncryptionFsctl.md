# FatEncryptionFsctl

- ea: `0x140036d14`
- end: `0x140036ff6`
- name: `FatEncryptionFsctl`
- size: `738`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140042ac0`

## callees

- `0x140002fd4`
- `0x14002d5a8`
- `0x140036d14`
- `0x140038eb4`
- `0x14003d880`
- `0x1400465f4`
- `0x1400466c8`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140036e23`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140036e46`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140036e23`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140036e46`
- `ntoskrnl!ProbeForRead` at `0x140036df8`
- `ntoskrnl!ProbeForRead` at `0x140036df8`
- `ntoskrnl!ProbeForWrite` at `0x140036e11`
- `ntoskrnl!ProbeForWrite` at `0x140036e11`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140036ead`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140036ead`
- `ntoskrnl!ExReleaseResourceLite` at `0x140036f97`
- `ntoskrnl!ExReleaseResourceLite` at `0x140036fa7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140036fbf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dad9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dafa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005db1e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140036f97`
- `ntoskrnl!ExReleaseResourceLite` at `0x140036fa7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140036fbf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dad9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dafa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005db1e`
- `ntoskrnl!ExRaiseStatus` at `0x140036e5c`
- `ntoskrnl!ExRaiseStatus` at `0x140036e5c`

## pseudocode

```c
__int64 __fastcall FatEncryptionFsctl(_DWORD *Entry, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  __int64 v5; // rcx
  unsigned int v6; // esi
  struct _ERESOURCE *v7; // r13
  PVOID v8; // rsi
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rax
  ULONG Options; // ecx
  int v11; // esi
  char v12; // r12
  __int64 v13; // r15
  int v14; // ecx
  __int64 v16; // [rsp+98h] [rbp-60h] BYREF
  __int64 v17; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v18; // [rsp+A8h] [rbp-50h] BYREF
  PVOID v19; // [rsp+B0h] [rbp-48h]
  PNAMED_PIPE_CREATE_PARAMETERS v20; // [rsp+B8h] [rbp-40h]
  SIZE_T Length; // [rsp+118h] [rbp+20h] BYREF

  v18 = 0;
  v16 = 0;
  v17 = 0;
  LODWORD(Length) = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Entry[17] |= 2u;
  if ( (unsigned int)FatDecodeFileObject(CurrentStackLocation->FileObject, &v18, &v16, &v17) - 2 <= 1 )
  {
    v7 = (struct _ERESOURCE *)v18;
    if ( (*(_DWORD *)(v18 + 200) & 0x400000) != 0 )
    {
      v8 = FatMapUserBuffer(v5, (__int64)Irp);
      v19 = v8;
      LODWORD(Length) = CurrentStackLocation->Parameters.Read.Length;
      Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
      v20 = Parameters;
      Options = CurrentStackLocation->Parameters.Create.Options;
      LODWORD(v17) = Options;
      if ( Irp->RequestorMode )
      {
        ProbeForRead(Parameters, Options, 1u);
        ProbeForWrite(v8, (unsigned int)Length, 1u);
      }
      v11 = 0;
      v12 = FatAcquireExclusiveVcb_Real(Entry, v7, 0);
      v13 = v16;
      FatAcquireExclusiveFcb(Entry, v16);
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v13 + 16), 1u);
      v14 = *(_DWORD *)(v13 + 192);
      if ( (v14 & 0x20000) != 0 )
        v11 = 2;
      if ( (v14 & 0x40000) != 0 )
        v11 |= 1u;
      v6 = EfsFileSystemControlCallback((_DWORD)v20, v17, (_DWORD)v19, (unsigned int)&Length, v11);
      ExReleaseResourceLite(*(PERESOURCE *)(v13 + 16));
      ExReleaseResourceLite(*(PERESOURCE *)(v13 + 8));
      if ( v12 )
        ExReleaseResourceLite(v7 + 5);
    }
    else
    {
      v6 = -1073741808;
    }
  }
  else
  {
    v6 = -1073741811;
  }
  FatCompleteRequest_Real(Entry, Irp);
  return v6;
}

```

## disassembly

```asm
0x140036d14  mov     rax, rsp
0x140036d17  mov     [rax+10h], rdx
0x140036d1b  mov     [rax+8], rcx
0x140036d1f  push    rbx
0x140036d20  push    rsi
0x140036d21  push    rdi
0x140036d22  push    r12
0x140036d24  push    r13
0x140036d26  push    r14
0x140036d28  push    r15
0x140036d2a  sub     rsp, 0C0h
0x140036d31  mov     rdi, rdx
0x140036d34  mov     rbx, rcx
0x140036d37  xor     r15d, r15d
0x140036d3a  mov     [rax-50h], r15
0x140036d3e  mov     [rax-60h], r15
0x140036d42  mov     [rax-58h], r15
0x140036d46  mov     [rax+20h], r15d
0x140036d4a  mov     r14, [rdx+0B8h]
0x140036d51  mov     [rax+18h], r15b
0x140036d55  or      dword ptr [rcx+44h], 2
0x140036d59  lea     r9, [rax-58h]
0x140036d5d  lea     r8, [rax-60h]
0x140036d61  lea     rdx, [rax-50h]
0x140036d65  mov     rcx, [r14+30h]
0x140036d69  call    FatDecodeFileObject
0x140036d6e  add     eax, 0FFFFFFFEh
0x140036d71  lea     r12d, [r15+1]
0x140036d75  cmp     eax, r12d
0x140036d78  jbe     short loc_140036D84
0x140036d7a  mov     esi, 0C000000Dh
0x140036d7f  jmp     loc_140036FD2
0x140036d84  mov     r13, [rsp+0F8h+var_50]
0x140036d8c  mov     eax, [r13+0C8h]
0x140036d93  bt      eax, 16h
0x140036d97  jnb     loc_140036FCD
0x140036d9d  mov     [rsp+0F8h+var_68], r15b
0x140036da5  mov     [rsp+0F8h+var_67], r15b
0x140036dad  mov     [rsp+0F8h+var_66], r15b
0x140036db5  mov     rdx, rdi
0x140036db8  call    FatMapUserBuffer
0x140036dbd  mov     rsi, rax
0x140036dc0  mov     [rsp+0F8h+var_48], rax
0x140036dc8  mov     ecx, [r14+8]
0x140036dcc  mov     dword ptr [rsp+0F8h+Length], ecx
0x140036dd3  mov     rax, [r14+20h]
0x140036dd7  mov     [rsp+0F8h+var_40], rax
0x140036ddf  mov     ecx, [r14+10h]
0x140036de3  mov     dword ptr [rsp+0F8h+var_58], ecx
0x140036dea  cmp     [rdi+40h], r15b
0x140036dee  jz      short loc_140036E69
0x140036df0  mov     edx, ecx; Length
0x140036df2  mov     r8d, r12d; Alignment
0x140036df5  mov     rcx, rax; Address
0x140036df8  call    cs:__imp_ProbeForRead
0x140036dff  nop     dword ptr [rax+rax+00h]
0x140036e04  mov     edx, dword ptr [rsp+0F8h+Length]; Length
0x140036e0b  mov     r8d, r12d; Alignment
0x140036e0e  mov     rcx, rsi; Address
0x140036e11  call    cs:__imp_ProbeForWrite
0x140036e18  nop     dword ptr [rax+rax+00h]
0x140036e1d  jmp     short loc_140036E69
0x140036e1f  mov     ebx, eax
0x140036e21  mov     ecx, eax; Exception
0x140036e23  call    cs:__imp_FsRtlIsNtstatusExpected
0x140036e2a  nop     dword ptr [rax+rax+00h]
0x140036e2f  mov     edx, 0C00000E8h
0x140036e34  test    al, al
0x140036e36  cmovnz  edx, ebx
0x140036e39  mov     rcx, [rsp+0F8h+arg_0]
0x140036e41  mov     [rcx+48h], edx
0x140036e44  mov     ecx, ebx; Exception
0x140036e46  call    cs:__imp_FsRtlIsNtstatusExpected
0x140036e4d  nop     dword ptr [rax+rax+00h]
0x140036e52  mov     ecx, 0C00000E8h
0x140036e57  test    al, al
0x140036e59  cmovnz  ecx, ebx; Status
0x140036e5c  call    cs:__imp_ExRaiseStatus
0x140036e69  mov     esi, r15d
0x140036e6c  mov     [rsp+0F8h+var_64], r15d
0x140036e74  xor     r8d, r8d
0x140036e77  mov     rdx, r13
0x140036e7a  mov     rcx, rbx
0x140036e7d  call    FatAcquireExclusiveVcb_Real
0x140036e82  mov     r12b, al
0x140036e85  mov     [rsp+0F8h+var_66], al
0x140036e8c  mov     r15, [rsp+0F8h+var_60]
0x140036e94  mov     rdx, r15
0x140036e97  mov     rcx, rbx
0x140036e9a  call    FatAcquireExclusiveFcb
0x140036e9f  mov     [rsp+0F8h+var_67], 1
0x140036ea7  mov     dl, 1; Wait
0x140036ea9  mov     rcx, [r15+10h]; Resource
0x140036ead  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140036eb4  nop     dword ptr [rax+rax+00h]
0x140036eb9  mov     edx, 1
0x140036ebe  mov     [rsp+0F8h+var_68], dl
0x140036ec5  mov     ecx, [r15+0C0h]
0x140036ecc  bt      ecx, 11h
0x140036ed0  lea     eax, [rdx+1]
0x140036ed3  cmovb   esi, eax
0x140036ed6  mov     [rsp+0F8h+var_64], esi
0x140036edd  bt      ecx, 12h
0x140036ee1  jnb     short loc_140036EEC
0x140036ee3  or      esi, edx
0x140036ee5  mov     [rsp+0F8h+var_64], esi
0x140036eec  mov     ecx, 503h
0x140036ef1  movzx   eax, word ptr [r15]
0x140036ef5  sub     ax, cx
0x140036ef8  cmp     ax, dx
0x140036efb  setbe   cl
0x140036efe  mov     r9d, [r13+0C8h]
0x140036f05  lea     rax, [r15+90h]
0x140036f0c  lea     r8, [r13-1A0h]
0x140036f13  shr     r9d, 0Eh
0x140036f17  and     r9d, edx
0x140036f1a  mov     [rsp+0F8h+var_78], rax
0x140036f22  lea     rax, [rsp+0F8h+arg_10]
0x140036f2a  mov     [rsp+0F8h+var_80], rax
0x140036f2f  mov     [rsp+0F8h+var_88], cl
0x140036f33  mov     [rsp+0F8h+var_90], r15
0x140036f38  mov     rax, [r13+88h]
0x140036f3f  mov     [rsp+0F8h+var_98], rax
0x140036f44  mov     [rsp+0F8h+var_A0], r8
0x140036f49  mov     [rsp+0F8h+var_A8], rbx
0x140036f4e  mov     rax, [rbx+28h]
0x140036f52  mov     [rsp+0F8h+var_B0], rax
0x140036f57  mov     [rsp+0F8h+var_B8], r15
0x140036f5c  mov     eax, [r14+18h]
0x140036f60  mov     [rsp+0F8h+var_C0], eax
0x140036f64  mov     [rsp+0F8h+var_C8], r9d
0x140036f69  mov     [rsp+0F8h+var_D8], esi
0x140036f6d  lea     r9, [rsp+0F8h+Length]
0x140036f75  mov     r8, [rsp+0F8h+var_48]
0x140036f7d  mov     edx, dword ptr [rsp+0F8h+var_58]
0x140036f84  mov     rcx, [rsp+0F8h+var_40]
0x140036f8c  call    EfsFileSystemControlCallback
0x140036f91  mov     esi, eax
0x140036f93  mov     rcx, [r15+10h]; Resource
0x140036f97  call    cs:__imp_ExReleaseResourceLite
0x140036f9e  nop     dword ptr [rax+rax+00h]
0x140036fa3  mov     rcx, [r15+8]; Resource
0x140036fa7  call    cs:__imp_ExReleaseResourceLite
0x140036fae  nop     dword ptr [rax+rax+00h]
0x140036fb3  test    r12b, r12b
0x140036fb6  jz      short loc_140036FD2
0x140036fb8  lea     rcx, [r13+208h]; Resource
0x140036fbf  call    cs:__imp_ExReleaseResourceLite
0x140036fc6  nop     dword ptr [rax+rax+00h]
0x140036fcb  jmp     short loc_140036FD2
0x140036fcd  mov     esi, 0C0000010h
0x140036fd2  mov     r8d, esi
0x140036fd5  mov     rdx, rdi; Irp
0x140036fd8  mov     rcx, rbx; Entry
0x140036fdb  call    FatCompleteRequest_Real
0x140036fe0  mov     eax, esi
0x140036fe2  add     rsp, 0C0h
0x140036fe9  pop     r15
0x140036feb  pop     r14
0x140036fed  pop     r13
0x140036fef  pop     r12
0x140036ff1  pop     rdi
0x140036ff2  pop     rsi
0x140036ff3  pop     rbx
0x140036ff4  retn
0x14005da94  push    rbp
0x14005da96  sub     rsp, 90h
0x14005da9d  mov     rbp, rdx
0x14005daa0  xor     eax, eax
0x14005daa2  mov     rcx, [rbp+108h]
0x14005daa9  cmp     [rcx+40h], al
0x14005daac  setnz   al
0x14005daaf  add     rsp, 90h
0x14005dab6  pop     rbp
0x14005dab7  retn
0x14005dab9  push    rbp
0x14005dabb  sub     rsp, 90h
0x14005dac2  mov     rbp, rdx
0x14005dac5  cmp     byte ptr [rbp+90h], 0
0x14005dacc  jz      short loc_14005DAE6
0x14005dace  mov     rcx, [rbp+98h]
0x14005dad5  mov     rcx, [rcx+10h]; Resource
0x14005dad9  call    cs:__imp_ExReleaseResourceLite
0x14005dae0  nop     dword ptr [rax+rax+00h]
0x14005dae5  nop
0x14005dae6  cmp     byte ptr [rbp+91h], 0
0x14005daed  jz      short loc_14005DB07
0x14005daef  mov     rcx, [rbp+98h]
0x14005daf6  mov     rcx, [rcx+8]; Resource
0x14005dafa  call    cs:__imp_ExReleaseResourceLite
0x14005db01  nop     dword ptr [rax+rax+00h]
0x14005db06  nop
0x14005db07  cmp     byte ptr [rbp+92h], 0
0x14005db0e  jz      short loc_14005DB2B
0x14005db10  mov     rcx, [rbp+0A8h]
0x14005db17  add     rcx, 208h; Resource
0x14005db1e  call    cs:__imp_ExReleaseResourceLite
0x14005db25  nop     dword ptr [rax+rax+00h]
0x14005db2a  nop
0x14005db2b  add     rsp, 90h
0x14005db32  pop     rbp
0x14005db33  retn
```
