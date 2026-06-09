# PrjfSendPostCreateNotifications

- ea: `0x140024758`
- end: `0x1400249d5`
- name: `PrjfSendPostCreateNotifications`
- size: `637`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, struct _FLT_INSTANCE *, struct _FILE_OBJECT *, __int64, __int64, int, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140023d68`

## callees

- `0x1400047cc`
- `0x14000ba20`
- `0x14000d128`
- `0x14000dab0`
- `0x140024758`

## import_xrefs

- `FLTMGR!FltQueryInformationFile` at `0x1400247bb`
- `FLTMGR!FltQueryInformationFile` at `0x1400247bb`

## string_xrefs

- `0x140024806`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140024953`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
__int64 __fastcall PrjfSendPostCreateNotifications(
        struct _FLT_CALLBACK_DATA *a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        _DWORD *a7)
{
  NTSTATUS v11; // eax
  int v12; // edx
  int v13; // r8d
  unsigned int v14; // edi
  ULONG_PTR Information; // rcx
  int v16; // r8d
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  PIO_SECURITY_CONTEXT SecurityContext; // rax
  int v19; // eax
  int v20; // edx
  int v21; // r8d
  __int128 v23; // [rsp+60h] [rbp-51h] BYREF
  __int128 v24; // [rsp+70h] [rbp-41h] BYREF
  __int64 v25; // [rsp+80h] [rbp-31h]
  __int128 FileInformation; // [rsp+88h] [rbp-29h] BYREF
  __int64 v27; // [rsp+98h] [rbp-19h]

  v27 = 0;
  FileInformation = 0;
  v11 = FltQueryInformationFile(a2, a3, &FileInformation, 0x18u, FileStandardInformation, 0);
  v14 = v11;
  if ( v11 < 0 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDqd(
        517,
        v12,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        12,
        (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
        205,
        (char)a3,
        v11);
    }
    return v14;
  }
  if ( (*(_DWORD *)(a4 + 56) & 0x10000) == 0 || HIWORD(v27) )
  {
    *a7 = 1;
    return v14;
  }
  v25 = 0;
  *a7 = a6;
  Information = a1->IoStatus.Information;
  v24 = 0;
  if ( Information == 2 )
  {
    v16 = 4;
  }
  else
  {
    if ( Information && Information != 3 )
      goto LABEL_10;
    v16 = 8;
  }
  if ( ((unsigned __int8)a6 & (unsigned __int8)v16) == 0 )
  {
LABEL_10:
    if ( (a6 & 2) == 0 )
      return v14;
    v16 = 2;
  }
  Iopb = a1->Iopb;
  SecurityContext = Iopb->Parameters.Create.SecurityContext;
  v23 = *(_OWORD *)a4;
  LODWORD(v24) = SecurityContext->DesiredAccess;
  DWORD1(v24) = Iopb->Parameters.Create.ShareAccess;
  DWORD2(v24) = HIBYTE(Iopb->Parameters.SetVolumeInformation.FsInformationClass);
  HIDWORD(v24) = Iopb->Parameters.Create.Options & 0xFFFFFF;
  LODWORD(v25) = a1->IoStatus.Information;
  v19 = PrjfSendNotifyOperationCommand(a1, a2, a3, &v23, a5, SBYTE5(v27), v16, 0, (__int64)&v24, 0, a7);
  v14 = v19;
  if ( v19 < 0 && ((xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
  {
    LOBYTE(v20) = xmmword_14001A3D0 & 0x20;
    LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      517,
      v20,
      v21,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      5,
      13,
      (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
      37,
      v19);
  }
  return v14;
}

```

## disassembly

```asm
0x140024758  push    rbp
0x14002475a  push    rbx
0x14002475b  push    rsi
0x14002475c  push    rdi
0x14002475d  push    r12
0x14002475f  push    r13
0x140024761  push    r14
0x140024763  push    r15
0x140024765  lea     rbp, [rsp-7]
0x14002476a  sub     rsp, 0B8h
0x140024771  mov     rax, cs:__security_cookie
0x140024778  xor     rax, rsp
0x14002477b  mov     [rbp+3Fh+var_50], rax
0x14002477f  mov     r13, [rbp+3Fh+arg_20]
0x140024783  xor     eax, eax
0x140024785  mov     rbx, [rbp+3Fh+arg_30]
0x140024789  mov     r15, r8
0x14002478c  mov     r12, rdx
0x14002478f  mov     [rsp+0F0h+LengthReturned], rax; LengthReturned
0x140024794  mov     r14, r9
0x140024797  mov     [rbp+3Fh+var_58], rax
0x14002479b  mov     rsi, rcx
0x14002479e  mov     [rsp+0F0h+FileInformationClass], 5; FileInformationClass
0x1400247a6  xorps   xmm0, xmm0
0x1400247a9  lea     r9d, [rax+18h]; Length
0x1400247ad  lea     r8, [rbp+3Fh+FileInformation]; FileInformation
0x1400247b1  mov     rdx, r15; FileObject
0x1400247b4  mov     rcx, r12; Instance
0x1400247b7  movups  [rbp+3Fh+FileInformation], xmm0
0x1400247bb  call    cs:__imp_FltQueryInformationFile
0x1400247c2  nop     dword ptr [rax+rax+00h]
0x1400247c7  xor     r9d, r9d
0x1400247ca  mov     edi, eax
0x1400247cc  test    eax, eax
0x1400247ce  jns     short loc_14002484D
0x1400247d0  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400247d6  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400247dd  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400247e4  setnz   r8b
0x1400247e8  and     dl, 20h
0x1400247eb  jnz     short loc_1400247F6
0x1400247ed  test    r8b, r8b
0x1400247f0  jz      loc_1400249B2
0x1400247f6  mov     r9, cs:WPP_GLOBAL_Control
0x1400247fd  mov     ecx, 205h
0x140024802  mov     [rsp+0F0h+var_98], eax
0x140024806  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002480d  mov     [rsp+0F0h+var_A0], r15
0x140024812  mov     [rsp+0F0h+var_A8], 0CDh
0x14002481a  mov     r9, [r9+40h]
0x14002481e  mov     [rsp+0F0h+var_B0], rax
0x140024823  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14002482a  mov     [rsp+0F0h+var_B8], rax
0x14002482f  mov     word ptr [rsp+0F0h+var_C0], 0Ch
0x140024836  mov     dword ptr [rsp+0F0h+LengthReturned], 5
0x14002483e  mov     byte ptr [rsp+0F0h+FileInformationClass], 2
0x140024843  call    WPP_RECORDER_AND_TRACE_SF_sDqd
0x140024848  jmp     loc_1400249B2
0x14002484d  test    dword ptr [r14+38h], 10000h
0x140024855  jz      loc_1400249AC
0x14002485b  cmp     byte ptr [rbp+3Fh+var_58+6], r9b
0x14002485f  jnz     loc_1400249AC
0x140024865  cmp     byte ptr [rbp+3Fh+var_58+7], r9b
0x140024869  jnz     loc_1400249AC
0x14002486f  mov     eax, [rbp+3Fh+arg_28]
0x140024872  xor     ecx, ecx
0x140024874  mov     [rbp+3Fh+var_70], rcx
0x140024878  xorps   xmm0, xmm0
0x14002487b  mov     [rbx], eax
0x14002487d  mov     rcx, [rsi+20h]
0x140024881  movups  [rbp+3Fh+var_80], xmm0
0x140024885  cmp     rcx, 2
0x140024889  jnz     loc_140024992
0x14002488f  lea     r8d, [rcx+2]
0x140024893  test    r8b, al
0x140024896  jnz     short loc_1400248A6
0x140024898  test    al, 2
0x14002489a  jz      loc_1400249B2
0x1400248a0  mov     r8d, 2
0x1400248a6  mov     rdx, [rsi+10h]
0x1400248aa  movups  xmm0, xmmword ptr [r14]
0x1400248ae  mov     [rsp+0F0h+var_A0], rbx
0x1400248b3  mov     byte ptr [rsp+0F0h+var_A8], r9b
0x1400248b8  mov     rax, [rdx+18h]
0x1400248bc  movdqu  [rbp+3Fh+var_90], xmm0
0x1400248c1  mov     ecx, [rax+10h]
0x1400248c4  mov     dword ptr [rbp+3Fh+var_80], ecx
0x1400248c7  mov     rcx, rsi
0x1400248ca  movzx   eax, word ptr [rdx+2Ah]
0x1400248ce  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x1400248d1  movzx   eax, byte ptr [rdx+23h]
0x1400248d5  mov     dword ptr [rbp+3Fh+var_80+8], eax
0x1400248d8  mov     eax, [rdx+20h]
0x1400248db  mov     rdx, r12
0x1400248de  and     eax, 0FFFFFFh
0x1400248e3  mov     dword ptr [rbp+3Fh+var_80+0Ch], eax
0x1400248e6  mov     eax, [rsi+20h]
0x1400248e9  mov     dword ptr [rbp+3Fh+var_70], eax
0x1400248ec  lea     rax, [rbp+3Fh+var_80]
0x1400248f0  mov     [rsp+0F0h+var_B0], rax
0x1400248f5  mov     al, byte ptr [rbp+3Fh+var_58+5]
0x1400248f8  mov     [rsp+0F0h+var_B8], r9
0x1400248fd  lea     r9, [rbp+3Fh+var_90]
0x140024901  mov     [rsp+0F0h+var_C0], r8d
0x140024906  mov     r8, r15
0x140024909  mov     byte ptr [rsp+0F0h+LengthReturned], al
0x14002490d  mov     qword ptr [rsp+0F0h+FileInformationClass], r13
0x140024912  call    PrjfSendNotifyOperationCommand
0x140024917  mov     edi, eax
0x140024919  test    eax, eax
0x14002491b  jns     loc_1400249B2
0x140024921  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140024927  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002492e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140024935  setnz   r8b
0x140024939  and     dl, 20h
0x14002493c  jnz     short loc_140024943
0x14002493e  test    r8b, r8b
0x140024941  jz      short loc_1400249B2
0x140024943  mov     r9, cs:WPP_GLOBAL_Control
0x14002494a  mov     ecx, 205h
0x14002494f  mov     dword ptr [rsp+0F0h+var_A0], eax
0x140024953  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002495a  mov     [rsp+0F0h+var_A8], 125h
0x140024962  mov     [rsp+0F0h+var_B0], rax
0x140024967  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14002496e  mov     r9, [r9+40h]
0x140024972  mov     [rsp+0F0h+var_B8], rax
0x140024977  mov     word ptr [rsp+0F0h+var_C0], 0Dh
0x14002497e  mov     dword ptr [rsp+0F0h+LengthReturned], 5
0x140024986  mov     byte ptr [rsp+0F0h+FileInformationClass], 2
0x14002498b  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140024990  jmp     short loc_1400249B2
0x140024992  test    rcx, rcx
0x140024995  jz      short loc_1400249A1
0x140024997  cmp     rcx, 3
0x14002499b  jnz     loc_140024898
0x1400249a1  mov     r8d, 8
0x1400249a7  jmp     loc_140024893
0x1400249ac  mov     dword ptr [rbx], 1
0x1400249b2  mov     eax, edi
0x1400249b4  mov     rcx, [rbp+3Fh+var_50]
0x1400249b8  xor     rcx, rsp; StackCookie
0x1400249bb  call    __security_check_cookie
0x1400249c0  add     rsp, 0B8h
0x1400249c7  pop     r15
0x1400249c9  pop     r14
0x1400249cb  pop     r13
0x1400249cd  pop     r12
0x1400249cf  pop     rdi
0x1400249d0  pop     rsi
0x1400249d1  pop     rbx
0x1400249d2  pop     rbp
0x1400249d3  retn
```
