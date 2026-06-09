# PrjfIsDirectoryEmpty

- ea: `0x14002a6b4`
- end: `0x14002aa1d`
- name: `PrjfIsDirectoryEmpty`
- size: `873`
- prototype: `__int64 __fastcall(__int64, struct _FLT_INSTANCE *, struct _FILE_OBJECT *, __int64, char *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140007300`
- `0x14003cc14`

## callees

- `0x140002f3c`
- `0x14000d128`
- `0x14000d5e8`
- `0x140021c5c`
- `0x140024b24`
- `0x14002a6b4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002a9b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a9b4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002a8da`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002a8f8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002a8da`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002a8f8`
- `ntoskrnl!ExAllocatePool2` at `0x14002a716`
- `ntoskrnl!ExAllocatePool2` at `0x14002a716`
- `FLTMGR!FltReleaseContext` at `0x14002a9c9`
- `FLTMGR!FltReleaseContext` at `0x14002a9e0`
- `FLTMGR!FltReleaseContext` at `0x14002a9f7`
- `FLTMGR!FltReleaseContext` at `0x14002a9c9`
- `FLTMGR!FltReleaseContext` at `0x14002a9e0`
- `FLTMGR!FltReleaseContext` at `0x14002a9f7`

## pseudocode

```c
__int64 __fastcall PrjfIsDirectoryEmpty(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        __int64 a4,
        char *a5)
{
  USHORT *v7; // rsi
  char v9; // di
  int v10; // edx
  int SetContextFileObject; // ebx
  int v12; // r8d
  int v13; // edx
  int v14; // r8d
  char v15; // al
  int v16; // edx
  int v17; // r8d
  __int64 v18; // rax
  PFLT_CONTEXT v19; // [rsp+68h] [rbp-11h] BYREF
  PFLT_CONTEXT v20; // [rsp+70h] [rbp-9h] BYREF
  __int64 Pool2; // [rsp+78h] [rbp-1h]
  PFLT_CONTEXT Context; // [rsp+80h] [rbp+7h] BYREF
  UNICODE_STRING String1; // [rsp+88h] [rbp+Fh] BYREF
  _QWORD v24[6]; // [rsp+98h] [rbp+1Fh] BYREF
  int v26; // [rsp+F0h] [rbp+77h] BYREF

  v24[0] = 262146;
  v26 = 0;
  v20 = 0;
  v19 = 0;
  v24[1] = L"*";
  Context = 0;
  String1 = 0;
  Pool2 = ExAllocatePool2(256, 0x10000, 1701071440);
  v7 = (USHORT *)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v9 = 1;
  SetContextFileObject = PrjfGetSetContextFileObject(a2, a3, 0x80000000, 1, 0, 0, 0, &v20, &v19);
  if ( SetContextFileObject >= 0 )
  {
    SetContextFileObject = PrjfGetSetStreamHandleContext(a2, a3, v20, v19, 0, &Context);
    if ( SetContextFileObject >= 0 )
    {
      v15 = 1;
LABEL_13:
      SetContextFileObject = PrjfEnumerateDirectoryWithMerge(
                               a1,
                               a2,
                               a3,
                               60,
                               (__int64)v24,
                               0,
                               v15,
                               0,
                               0x10000u,
                               (__int64)v7,
                               &v26);
      if ( SetContextFileObject < 0 )
      {
        if ( SetContextFileObject != -2147483642 )
        {
          if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v16) = BYTE1(xmmword_14001A3D0) & 4;
            LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDdd(522, v16, v17, *((_QWORD *)WPP_GLOBAL_Control + 8));
          }
          goto LABEL_26;
        }
        SetContextFileObject = 0;
      }
      else
      {
        while ( 1 )
        {
          String1.Buffer = v7 + 44;
          String1.Length = v7[30];
          String1.MaximumLength = String1.Length;
          if ( !RtlEqualUnicodeString(&String1, &stru_140015550, 1u)
            && !RtlEqualUnicodeString(&String1, &stru_140015540, 1u) )
          {
            break;
          }
          v18 = *(unsigned int *)v7;
          if ( !(_DWORD)v18 )
          {
            v7 = (USHORT *)Pool2;
            v15 = 0;
            goto LABEL_13;
          }
          v7 = (USHORT *)((char *)v7 + v18);
        }
        v7 = (USHORT *)Pool2;
        v9 = 0;
      }
      *a5 = v9;
    }
    else if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0
           || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = BYTE1(xmmword_14001A3D0) & 0x20;
      LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        525,
        v13,
        v14,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        13,
        42,
        (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
        70,
        SetContextFileObject);
    }
  }
  else if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 0x20;
    LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      525,
      v10,
      v12,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      13,
      41,
      (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
      57,
      SetContextFileObject);
  }
LABEL_26:
  ExFreePoolWithTag(v7, 0x65644A50u);
  if ( Context )
    FltReleaseContext(Context);
  if ( v19 )
    FltReleaseContext(v19);
  if ( v20 )
    FltReleaseContext(v20);
  return (unsigned int)SetContextFileObject;
}

```

## disassembly

```asm
0x14002a6b4  mov     rax, rsp
0x14002a6b7  mov     [rax+10h], rbx
0x14002a6bb  mov     [rax+20h], r9d
0x14002a6bf  mov     [rax+8], rcx
0x14002a6c3  push    rbp
0x14002a6c4  push    rsi
0x14002a6c5  push    rdi
0x14002a6c6  push    r12
0x14002a6c8  push    r13
0x14002a6ca  lea     rbp, [rax-57h]
0x14002a6ce  sub     rsp, 0A0h
0x14002a6d5  xor     ebx, ebx
0x14002a6d7  mov     [rbp+4Fh+var_30], 40002h
0x14002a6df  mov     r12, r8
0x14002a6e2  mov     [rbp+4Fh+arg_18], ebx
0x14002a6e5  mov     r13, rdx
0x14002a6e8  mov     [rbp+4Fh+var_58], rbx
0x14002a6ec  lea     rax, asc_140015960; "*"
0x14002a6f3  mov     [rbp+4Fh+var_60], rbx
0x14002a6f7  xorps   xmm0, xmm0
0x14002a6fa  mov     [rbp+4Fh+var_28], rax
0x14002a6fe  mov     edx, 10000h
0x14002a703  mov     [rbp+4Fh+Context], rbx
0x14002a707  mov     r8d, 65644A50h
0x14002a70d  mov     ecx, 100h
0x14002a712  movups  xmmword ptr [rbp+4Fh+String1.Length], xmm0
0x14002a716  call    cs:__imp_ExAllocatePool2
0x14002a71d  nop     dword ptr [rax+rax+00h]
0x14002a722  mov     [rbp+4Fh+var_50], rax
0x14002a726  mov     rsi, rax
0x14002a729  test    rax, rax
0x14002a72c  jnz     short loc_14002A738
0x14002a72e  mov     eax, 0C000009Ah
0x14002a733  jmp     loc_14002AA05
0x14002a738  lea     rax, [rbp+4Fh+var_60]
0x14002a73c  mov     dil, 1
0x14002a73f  mov     [rsp+0C0h+var_80], rax; __int64
0x14002a744  mov     r9b, dil
0x14002a747  lea     rax, [rbp+4Fh+var_58]
0x14002a74b  mov     r8d, 80000000h
0x14002a751  mov     [rsp+0C0h+var_88], rax; __int64
0x14002a756  mov     rdx, r12; FileObject
0x14002a759  mov     [rsp+0C0h+var_90], rbx; __int64
0x14002a75e  mov     rcx, r13; Instance
0x14002a761  mov     [rsp+0C0h+var_98], rbx; __int64
0x14002a766  mov     [rsp+0C0h+var_A0], bl; char
0x14002a76a  call    PrjfGetSetContextFileObject
0x14002a76f  mov     ebx, eax
0x14002a771  test    eax, eax
0x14002a773  jns     short loc_14002A7ED
0x14002a775  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002a77b  lea     rax, WPP_RECORDER_INITIALIZED
0x14002a782  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002a789  setnz   r8b
0x14002a78d  and     dl, 20h
0x14002a790  jnz     short loc_14002A79B
0x14002a792  test    r8b, r8b
0x14002a795  jz      loc_14002A9AC
0x14002a79b  mov     [rsp+0C0h+var_70], ebx
0x14002a79f  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002a7a6  mov     dword ptr [rsp+0C0h+var_78], 0C39h
0x14002a7ae  mov     [rsp+0C0h+var_80], rax
0x14002a7b3  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002a7ba  mov     [rsp+0C0h+var_88], rax
0x14002a7bf  mov     word ptr [rsp+0C0h+var_90], 29h ; ')'
0x14002a7c6  mov     r9, cs:WPP_GLOBAL_Control
0x14002a7cd  mov     ecx, 20Dh
0x14002a7d2  mov     dword ptr [rsp+0C0h+var_98], 0Dh
0x14002a7da  mov     [rsp+0C0h+var_A0], 2
0x14002a7df  mov     r9, [r9+40h]
0x14002a7e3  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002a7e8  jmp     loc_14002A9AC
0x14002a7ed  mov     r9, [rbp+4Fh+var_60]
0x14002a7f1  lea     rax, [rbp+4Fh+Context]
0x14002a7f5  mov     r8, [rbp+4Fh+var_58]; Context
0x14002a7f9  mov     rdx, r12; FileObject
0x14002a7fc  mov     [rsp+0C0h+var_98], rax; __int64
0x14002a801  mov     rcx, r13; Instance
0x14002a804  mov     [rsp+0C0h+var_A0], 0; char
0x14002a809  call    PrjfGetSetStreamHandleContext
0x14002a80e  mov     ebx, eax
0x14002a810  test    eax, eax
0x14002a812  jns     short loc_14002A86A
0x14002a814  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002a81a  lea     rax, WPP_RECORDER_INITIALIZED
0x14002a821  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002a828  setnz   r8b
0x14002a82c  and     dl, 20h
0x14002a82f  jnz     short loc_14002A83A
0x14002a831  test    r8b, r8b
0x14002a834  jz      loc_14002A9AC
0x14002a83a  mov     [rsp+0C0h+var_70], ebx
0x14002a83e  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002a845  mov     dword ptr [rsp+0C0h+var_78], 0C46h
0x14002a84d  mov     [rsp+0C0h+var_80], rax
0x14002a852  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002a859  mov     [rsp+0C0h+var_88], rax
0x14002a85e  mov     word ptr [rsp+0C0h+var_90], 2Ah ; '*'
0x14002a865  jmp     loc_14002A7C6
0x14002a86a  mov     al, dil
0x14002a86d  lea     rcx, [rbp+4Fh+arg_18]
0x14002a871  mov     r9d, 3Ch ; '<'
0x14002a877  mov     qword ptr [rsp+0C0h+var_70], rcx
0x14002a87c  mov     r8, r12
0x14002a87f  mov     rcx, [rbp+4Fh+arg_0]
0x14002a883  mov     rdx, r13
0x14002a886  mov     [rsp+0C0h+var_78], rsi
0x14002a88b  mov     dword ptr [rsp+0C0h+var_80], 10000h
0x14002a893  mov     byte ptr [rsp+0C0h+var_88], 0
0x14002a898  mov     byte ptr [rsp+0C0h+var_90], al
0x14002a89c  lea     rax, [rbp+4Fh+var_30]
0x14002a8a0  mov     dword ptr [rsp+0C0h+var_98], 0
0x14002a8a8  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14002a8ad  call    PrjfEnumerateDirectoryWithMerge
0x14002a8b2  mov     ebx, eax
0x14002a8b4  test    eax, eax
0x14002a8b6  js      short loc_14002A927
0x14002a8b8  lea     rax, [rsi+58h]
0x14002a8bc  mov     r8b, dil; CaseInSensitive
0x14002a8bf  mov     [rbp+4Fh+String1.Buffer], rax
0x14002a8c3  lea     rdx, stru_140015550; String2
0x14002a8ca  movzx   eax, word ptr [rsi+3Ch]
0x14002a8ce  lea     rcx, [rbp+4Fh+String1]; String1
0x14002a8d2  mov     [rbp+4Fh+String1.Length], ax
0x14002a8d6  mov     [rbp+4Fh+String1.MaximumLength], ax
0x14002a8da  call    cs:__imp_RtlEqualUnicodeString
0x14002a8e1  nop     dword ptr [rax+rax+00h]
0x14002a8e6  test    al, al
0x14002a8e8  jnz     short loc_14002A908
0x14002a8ea  mov     r8b, dil; CaseInSensitive
0x14002a8ed  lea     rdx, stru_140015540; String2
0x14002a8f4  lea     rcx, [rbp+4Fh+String1]; String1
0x14002a8f8  call    cs:__imp_RtlEqualUnicodeString
0x14002a8ff  nop     dword ptr [rax+rax+00h]
0x14002a904  test    al, al
0x14002a906  jz      short loc_14002A91E
0x14002a908  mov     eax, [rsi]
0x14002a90a  test    eax, eax
0x14002a90c  jz      short loc_14002A913
0x14002a90e  add     rsi, rax
0x14002a911  jmp     short loc_14002A8B8
0x14002a913  mov     rsi, [rbp+4Fh+var_50]
0x14002a917  xor     al, al
0x14002a919  jmp     loc_14002A86D
0x14002a91e  mov     rsi, [rbp+4Fh+var_50]
0x14002a922  xor     dil, dil
0x14002a925  jmp     short loc_14002A931
0x14002a927  cmp     ebx, 80000006h
0x14002a92d  jnz     short loc_14002A93A
0x14002a92f  xor     ebx, ebx
0x14002a931  mov     rax, [rbp+4Fh+arg_20]
0x14002a935  mov     [rax], dil
0x14002a938  jmp     short loc_14002A9AC
0x14002a93a  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002a940  lea     rax, WPP_RECORDER_INITIALIZED
0x14002a947  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002a94e  setnz   r8b
0x14002a952  and     dl, 4
0x14002a955  jnz     short loc_14002A95C
0x14002a957  test    r8b, r8b
0x14002a95a  jz      short loc_14002A9AC
0x14002a95c  mov     r9, cs:WPP_GLOBAL_Control
0x14002a963  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002a96a  mov     [rsp+58h], ebx
0x14002a96e  mov     ecx, 20Ah
0x14002a973  mov     [rsp+0C0h+var_70], 2
0x14002a97b  mov     dword ptr [rsp+0C0h+var_78], 0C9Fh
0x14002a983  mov     r9, [r9+40h]
0x14002a987  mov     [rsp+0C0h+var_80], rax
0x14002a98c  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002a993  mov     [rsp+0C0h+var_88], rax
0x14002a998  mov     word ptr [rsp+0C0h+var_90], 2Ch ; ','
0x14002a99f  mov     dword ptr [rsp+0C0h+var_98], 0Ah
0x14002a9a7  call    WPP_RECORDER_AND_TRACE_SF_sDdd
0x14002a9ac  mov     edx, 65644A50h; Tag
0x14002a9b1  mov     rcx, rsi; P
0x14002a9b4  call    cs:__imp_ExFreePoolWithTag
0x14002a9bb  nop     dword ptr [rax+rax+00h]
0x14002a9c0  mov     rcx, [rbp+4Fh+Context]; Context
0x14002a9c4  test    rcx, rcx
0x14002a9c7  jz      short loc_14002A9D5
0x14002a9c9  call    cs:__imp_FltReleaseContext
0x14002a9d0  nop     dword ptr [rax+rax+00h]
0x14002a9d5  cmp     [rbp+4Fh+var_60], 0
0x14002a9da  jz      short loc_14002A9EC
0x14002a9dc  mov     rcx, [rbp+4Fh+var_60]; Context
0x14002a9e0  call    cs:__imp_FltReleaseContext
0x14002a9e7  nop     dword ptr [rax+rax+00h]
0x14002a9ec  cmp     [rbp+4Fh+var_58], 0
0x14002a9f1  jz      short loc_14002AA03
0x14002a9f3  mov     rcx, [rbp+4Fh+var_58]; Context
0x14002a9f7  call    cs:__imp_FltReleaseContext
0x14002a9fe  nop     dword ptr [rax+rax+00h]
0x14002aa03  mov     eax, ebx
0x14002aa05  mov     rbx, [rsp+0C0h+arg_8]
0x14002aa0d  add     rsp, 0A0h
0x14002aa14  pop     r13
0x14002aa16  pop     r12
0x14002aa18  pop     rdi
0x14002aa19  pop     rsi
0x14002aa1a  pop     rbp
0x14002aa1b  retn
```
