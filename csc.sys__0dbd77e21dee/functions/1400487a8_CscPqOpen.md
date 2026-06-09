# CscPqOpen

- ea: `0x1400487a8`
- end: `0x1400489d7`
- name: `CscPqOpen`
- size: `559`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140059edc`

## callees

- `0x140007ff8`
- `0x14000b9d0`
- `0x14002ab44`
- `0x14002cd0c`
- `0x14002cdbc`
- `0x14002d158`
- `0x14004635c`
- `0x1400487a8`

## import_xrefs

- `ntoskrnl!RtlValidateUnicodeString` at `0x140048831`
- `ntoskrnl!RtlValidateUnicodeString` at `0x140048831`

## pseudocode

```c
__int64 __fastcall CscPqOpen(
        __int64 *a1,
        __int64 a2,
        struct _LIST_ENTRY *a3,
        UNICODE_STRING *a4,
        struct _LIST_ENTRY *a5,
        char *a6,
        _BYTE *a7)
{
  char v7; // r14
  char v8; // bp
  __int64 v9; // rdi
  int v13; // eax
  int Header; // ebx
  int v15; // esi
  char *v16; // rax
  int v18; // [rsp+20h] [rbp-A8h]
  int v19; // [rsp+28h] [rbp-A0h]
  struct _LIST_ENTRY v20; // [rsp+70h] [rbp-58h] BYREF
  __int64 v21; // [rsp+D0h] [rbp+8h] BYREF

  v20.Flink = (struct _LIST_ENTRY *)-1LL;
  v7 = 0;
  v21 = 0;
  v8 = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_DqZ(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      (unsigned int)WPP_eb62243048b93ac38d7f5193621ee294_Traceguids,
      (_DWORD)a4,
      (char)a3,
      (__int64)a4);
  if ( !a4 || !a4->Length || RtlValidateUnicodeString(0, a4) < 0 )
  {
    Header = -1073741583;
    v15 = 597;
    goto LABEL_24;
  }
  v13 = CscPqpCreateHandle(&v21);
  v9 = v21;
  Header = v13;
  if ( v13 < 0 )
  {
    v15 = 601;
    goto LABEL_21;
  }
  Header = CscStorepLowIoCreateFilePoster(
             (struct _LIST_ENTRY *)(v21 + 8),
             a3,
             (struct _LIST_ENTRY *)a4,
             1180063,
             0,
             128,
             7,
             3,
             96,
             0,
             0,
             a5,
             &v20);
  if ( Header < 0 )
  {
    v15 = 616;
    goto LABEL_21;
  }
  if ( v20.Flink == (struct _LIST_ENTRY *)2 )
  {
    v7 = 1;
    Header = CscPqpInitializeFile(v9);
    if ( Header < 0 )
    {
      v15 = 623;
      goto LABEL_21;
    }
LABEL_20:
    v15 = 0;
    goto LABEL_24;
  }
  Header = CscPqpReadHeader(v9);
  if ( Header >= 0 )
  {
    v8 = *(_BYTE *)(v9 + 88);
    if ( !v8 && !*(_BYTE *)(v9 + 32) )
      goto LABEL_20;
    Header = CscPqpInitializeFile(v9);
    if ( Header >= 0 )
      goto LABEL_20;
    v15 = 640;
  }
  else
  {
    v15 = 628;
  }
LABEL_21:
  if ( v9 )
  {
    CscPqpDestroyHandle(&v21);
    v9 = v21;
  }
LABEL_24:
  v16 = a6;
  *a1 = v9;
  *v16 = v7;
  if ( a7 )
    *a7 = v8;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    LOBYTE(a2) = v8 != 0 ? 89 : 78;
    LOBYTE(v19) = a2;
    LOBYTE(v18) = v7 != 0 ? 89 : 78;
    WPP_SF_qccDD(WPP_GLOBAL_Control->AttachedDevice, a2, a3, v9, v18, v19, Header, v15);
  }
  return (unsigned int)Header;
}

```

## disassembly

```asm
0x1400487a8  mov     rax, rsp
0x1400487ab  push    rbx
0x1400487ac  push    rbp
0x1400487ad  push    rsi
0x1400487ae  push    rdi
0x1400487af  push    r12
0x1400487b1  push    r13
0x1400487b3  push    r14
0x1400487b5  push    r15
0x1400487b7  sub     rsp, 88h
0x1400487be  xor     r13d, r13d
0x1400487c1  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFFh
0x1400487c9  mov     r14b, r13b
0x1400487cc  mov     [rax+8], r13
0x1400487d0  mov     bpl, r13b
0x1400487d3  mov     edi, r13d
0x1400487d6  mov     rsi, r9
0x1400487d9  mov     r15, r8
0x1400487dc  mov     r12, rcx
0x1400487df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400487e6  lea     rax, WPP_GLOBAL_Control
0x1400487ed  cmp     rcx, rax
0x1400487f0  jz      short loc_140048819
0x1400487f2  test    dword ptr [rcx+2Ch], 40000h
0x1400487f9  jz      short loc_140048819
0x1400487fb  mov     rcx, [rcx+18h]
0x1400487ff  lea     edx, [r13+10h]
0x140048803  mov     [rsp+0C8h+var_A0], r9
0x140048808  mov     [rsp+0C8h+var_A8], r8
0x14004880d  lea     r8, WPP_eb62243048b93ac38d7f5193621ee294_Traceguids
0x140048814  call    WPP_SF_DqZ
0x140048819  test    rsi, rsi
0x14004881c  jz      loc_14004894B
0x140048822  cmp     [rsi], r13w
0x140048826  jz      loc_14004894B
0x14004882c  mov     rdx, rsi; String
0x14004882f  xor     ecx, ecx; Flags
0x140048831  call    cs:__imp_RtlValidateUnicodeString
0x140048838  nop     dword ptr [rax+rax+00h]
0x14004883d  test    eax, eax
0x14004883f  js      loc_14004894B
0x140048845  lea     rcx, [rsp+0C8h+arg_0]
0x14004884d  call    CscPqpCreateHandle
0x140048852  mov     rdi, [rsp+0C8h+arg_0]
0x14004885a  mov     ebx, eax
0x14004885c  test    eax, eax
0x14004885e  jns     short loc_14004886A
0x140048860  mov     esi, 259h
0x140048865  jmp     loc_14004892F
0x14004886a  lea     rax, [rsp+0C8h+var_58]
0x14004886f  mov     r9d, 12019Fh
0x140048875  mov     [rsp+0C8h+var_68], rax
0x14004887a  lea     rcx, [rdi+8]
0x14004887e  mov     rax, [rsp+0C8h+arg_20]
0x140048886  mov     r8, rsi
0x140048889  mov     [rsp+0C8h+var_70], rax
0x14004888e  mov     rdx, r15
0x140048891  mov     [rsp+0C8h+var_78], r13d
0x140048896  mov     [rsp+0C8h+var_80], r13
0x14004889b  mov     [rsp+0C8h+var_88], 60h ; '`'
0x1400488a3  mov     [rsp+0C8h+var_90], 3
0x1400488ab  mov     [rsp+0C8h+var_98], 7
0x1400488b3  mov     dword ptr [rsp+0C8h+var_A0], 80h
0x1400488bb  mov     [rsp+0C8h+var_A8], r13
0x1400488c0  call    CscStorepLowIoCreateFilePoster
0x1400488c5  mov     ebx, eax
0x1400488c7  test    eax, eax
0x1400488c9  jns     short loc_1400488D2
0x1400488cb  mov     esi, 268h
0x1400488d0  jmp     short loc_14004892F
0x1400488d2  cmp     qword ptr [rsp+0C8h+var_58], 2
0x1400488d8  mov     rcx, rdi
0x1400488db  jnz     short loc_1400488F2
0x1400488dd  mov     r14b, 1
0x1400488e0  call    CscPqpInitializeFile
0x1400488e5  mov     ebx, eax
0x1400488e7  test    eax, eax
0x1400488e9  jns     short loc_140048928
0x1400488eb  mov     esi, 26Fh
0x1400488f0  jmp     short loc_14004892F
0x1400488f2  call    CscPqpReadHeader
0x1400488f7  mov     ebx, eax
0x1400488f9  test    eax, eax
0x1400488fb  jns     short loc_140048904
0x1400488fd  mov     esi, 274h
0x140048902  jmp     short loc_14004892F
0x140048904  mov     bpl, [rdi+58h]
0x140048908  test    bpl, bpl
0x14004890b  jnz     short loc_140048913
0x14004890d  cmp     [rdi+20h], r13b
0x140048911  jz      short loc_140048928
0x140048913  mov     rcx, rdi
0x140048916  call    CscPqpInitializeFile
0x14004891b  mov     ebx, eax
0x14004891d  test    eax, eax
0x14004891f  jns     short loc_140048928
0x140048921  mov     esi, 280h
0x140048926  jmp     short loc_14004892F
0x140048928  mov     esi, r13d
0x14004892b  test    ebx, ebx
0x14004892d  jns     short loc_140048955
0x14004892f  test    rdi, rdi
0x140048932  jz      short loc_140048955
0x140048934  lea     rcx, [rsp+0C8h+arg_0]
0x14004893c  call    CscPqpDestroyHandle
0x140048941  mov     rdi, [rsp+0C8h+arg_0]
0x140048949  jmp     short loc_140048955
0x14004894b  mov     ebx, 0C00000F1h
0x140048950  mov     esi, 255h
0x140048955  mov     rax, [rsp+0C8h+arg_28]
0x14004895d  mov     [r12], rdi
0x140048961  mov     [rax], r14b
0x140048964  mov     rax, [rsp+0C8h+arg_30]
0x14004896c  test    rax, rax
0x14004896f  jz      short loc_140048974
0x140048971  mov     [rax], bpl
0x140048974  mov     rcx, cs:WPP_GLOBAL_Control
0x14004897b  lea     rax, WPP_GLOBAL_Control
0x140048982  cmp     rcx, rax
0x140048985  jz      short loc_1400489C0
0x140048987  test    dword ptr [rcx+2Ch], 40000h
0x14004898e  jz      short loc_1400489C0
0x140048990  mov     rcx, [rcx+18h]
0x140048994  neg     bpl
0x140048997  mov     [rsp+0C8h+var_90], esi
0x14004899b  mov     r9, rdi
0x14004899e  sbb     dl, dl
0x1400489a0  mov     [rsp+0C8h+var_98], ebx
0x1400489a4  and     dl, 0Bh
0x1400489a7  add     dl, 4Eh ; 'N'
0x1400489aa  neg     r14b
0x1400489ad  mov     byte ptr [rsp+0C8h+var_A0], dl
0x1400489b1  sbb     al, al
0x1400489b3  and     al, 0Bh
0x1400489b5  add     al, 4Eh ; 'N'
0x1400489b7  mov     byte ptr [rsp+0C8h+var_A8], al
0x1400489bb  call    WPP_SF_qccDD
0x1400489c0  mov     eax, ebx
0x1400489c2  add     rsp, 88h
0x1400489c9  pop     r15
0x1400489cb  pop     r14
0x1400489cd  pop     r13
0x1400489cf  pop     r12
0x1400489d1  pop     rdi
0x1400489d2  pop     rsi
0x1400489d3  pop     rbp
0x1400489d4  pop     rbx
0x1400489d5  retn
```
