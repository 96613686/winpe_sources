# PrjfFsctlSetReparsePoint

- ea: `0x14002d988`
- end: `0x14002e19b`
- name: `PrjfFsctlSetReparsePoint`
- size: `2067`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, __int64, int, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14002ec30`

## callees

- `0x140002b50`
- `0x140003a8c`
- `0x140004160`
- `0x14000b1d0`
- `0x14000d128`
- `0x14000d26c`
- `0x14000d754`
- `0x14000f0e8`
- `0x14000f4e4`
- `0x14000f984`
- `0x140029214`
- `0x14002d988`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002e145`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e145`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x14002dc09`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x14002dc09`
- `FLTMGR!FltReleaseContext` at `0x14002e159`
- `FLTMGR!FltReleaseContext` at `0x14002e16d`
- `FLTMGR!FltReleaseContext` at `0x14002e159`
- `FLTMGR!FltReleaseContext` at `0x14002e16d`

## pseudocode

```c
__int64 __fastcall PrjfFsctlSetReparsePoint(struct _FLT_CALLBACK_DATA *a1, __int64 a2, int a3, _QWORD *a4)
{
  struct _FLT_INSTANCE *v5; // rdx
  struct _FLT_CALLBACK_DATA *v6; // r15
  unsigned int v7; // r14d
  int IsNameOnPathOfRoot; // eax
  int v9; // edx
  int v10; // r8d
  int v11; // ebx
  int v12; // esi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  struct _REPARSE_DATA_BUFFER *Parameters; // rdi
  ULONG Options; // ecx
  int v16; // edx
  int v17; // r8d
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  int v21; // r8d
  int v22; // edx
  int v23; // r8d
  int v25; // [rsp+28h] [rbp-69h]
  int v26; // [rsp+28h] [rbp-69h]
  int v27; // [rsp+30h] [rbp-61h]
  int v28; // [rsp+38h] [rbp-59h]
  int v29; // [rsp+40h] [rbp-51h]
  int v30; // [rsp+48h] [rbp-49h]
  int v31; // [rsp+50h] [rbp-41h]
  char v32; // [rsp+78h] [rbp-19h]
  _DWORD *v33; // [rsp+90h] [rbp-1h]
  PVOID P[2]; // [rsp+98h] [rbp+7h]

  v5 = *(struct _FLT_INSTANCE **)(a2 + 24);
  v6 = a1;
  v7 = 1;
  *(_OWORD *)P = 0;
  IsNameOnPathOfRoot = PrjfIsNameOnPathOfRoot(a1, v5);
  v11 = IsNameOnPathOfRoot;
  if ( IsNameOnPathOfRoot != -1073741275 )
  {
    v12 = 3;
    if ( IsNameOnPathOfRoot == -1071906811 )
    {
      v32 = 1;
      if ( (BYTE8(xmmword_14001A3D0) & 0x80) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = BYTE8(xmmword_14001A3D0) & 0x80;
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDZ(
          775,
          v9,
          v10,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          3,
          7,
          10,
          (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
          130,
          *(_QWORD *)(a2 + 32) + 88LL);
      }
    }
    else
    {
      v32 = 0;
      if ( IsNameOnPathOfRoot < 0 )
      {
        if ( (xmmword_14001A3D0 & 0x80) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v9) = xmmword_14001A3D0 & 0x80;
          LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdZ(
            519,
            v9,
            v10,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            7,
            11,
            (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
            137,
            IsNameOnPathOfRoot,
            *(_QWORD *)(a2 + 32) + 88LL);
        }
        goto LABEL_14;
      }
    }
    Iopb = a1->Iopb;
    Parameters = (struct _REPARSE_DATA_BUFFER *)Iopb->Parameters.CreatePipe.Parameters;
    if ( Parameters )
    {
      Options = Iopb->Parameters.Create.Options;
      if ( a3 == 590860 )
      {
        if ( Options < 0x20 )
        {
          v11 = -1073741306;
          if ( (xmmword_14001A3D0 & 0x80) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v9) = xmmword_14001A3D0 & 0x80;
            LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDdZ(
              519,
              v9,
              v10,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              7,
              13,
              (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
              167,
              6,
              *(_QWORD *)(a2 + 32) + 88LL);
          }
          goto LABEL_14;
        }
        v33 = Iopb->Parameters.CreatePipe.Parameters;
        Parameters = (struct _REPARSE_DATA_BUFFER *)((char *)Parameters + 32);
        Options -= 32;
      }
      else
      {
        v33 = 0;
      }
      v11 = FsRtlValidateReparsePointBuffer(Options, Parameters);
      if ( v11 >= 0 )
      {
        if ( v32 && Parameters->ReparseTag == -1879048164 )
        {
          v7 = 4;
          v11 = -1073689083;
          if ( (BYTE8(xmmword_14001A3D0) & 0x80) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v16) = BYTE8(xmmword_14001A3D0) & 0x80;
            LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDL(
              775,
              v16,
              v17,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              3,
              7,
              15,
              (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
              216,
              5);
          }
          goto LABEL_57;
        }
        if ( !(unsigned __int8)PrjfGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32)) )
        {
          if ( Parameters->ReparseTag == -1879048164 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(v19, v18, v20);
          goto LABEL_57;
        }
        if ( Parameters->ReparseTag == -1879048164 )
        {
          if ( MEMORY[0] )
          {
            v7 = 0;
            *a4 = 0;
          }
          else
          {
            v11 = -1073741790;
            v7 = 4;
            if ( (xmmword_14001A3E0 & 0x80) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v18) = xmmword_14001A3E0 & 0x80;
              LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDdZ(
                1031,
                v18,
                v20,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                4,
                7,
                17,
                (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
                24,
                34,
                *(_QWORD *)(a2 + 32) + 88LL);
            }
          }
          goto LABEL_57;
        }
        if ( MEMORY[0x40] == 3 )
          goto LABEL_57;
        if ( MEMORY[0] )
        {
          if ( MEMORY[0] == 1 )
          {
            v7 = 4;
            v11 = -1073689083;
            if ( (xmmword_14001A3E0 & 0x80) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v18) = xmmword_14001A3E0 & 0x80;
              LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDdZ(
                1031,
                v18,
                v20,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                4,
                7,
                21,
                (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
                165,
                5,
                *(_QWORD *)(a2 + 32) + 88LL);
            }
          }
          goto LABEL_57;
        }
        if ( a3 != 589988 )
        {
          v21 = v33[1];
          if ( v21 )
          {
            if ( v21 != -1879048164 )
            {
              if ( (xmmword_14001A3E0 & 0x80) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                LOBYTE(v18) = xmmword_14001A3E0 & 0x80;
                WPP_RECORDER_AND_TRACE_SF_sDZDDD(
                  *(_DWORD *)(a2 + 32) + 88,
                  v18,
                  v21,
                  *((_QWORD *)WPP_GLOBAL_Control + 8),
                  v25,
                  v27,
                  v28,
                  v29,
                  v30,
                  v31,
                  *(_QWORD *)(a2 + 32) + 88LL,
                  v33[1],
                  *v33,
                  Parameters->ReparseTag);
              }
              goto LABEL_57;
            }
            v12 = 2;
          }
        }
        v11 = PrjfExpandAndWait(
                a1,
                *(struct _FLT_INSTANCE **)(a2 + 24),
                *(struct _FILE_OBJECT **)(a2 + 32),
                0,
                v12,
                1,
                15,
                1);
        if ( v11 >= 0 )
        {
LABEL_57:
          v6 = a1;
          goto LABEL_58;
        }
        if ( (xmmword_14001A3D0 & 0x80) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v22) = xmmword_14001A3D0 & 0x80;
          LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdLZ(
            519,
            v22,
            v23,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v26,
            7,
            20,
            (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
            140,
            v11,
            v12,
            *(_QWORD *)(a2 + 32) + 88LL);
        }
        v11 = -1073741790;
      }
    }
    else
    {
      v11 = -1073741306;
      if ( (xmmword_14001A3D0 & 0x80) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = xmmword_14001A3D0 & 0x80;
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          519,
          v9,
          v10,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          7,
          12,
          (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
          152,
          6,
          *(_QWORD *)(a2 + 32) + 88LL);
      }
    }
LABEL_14:
    v7 = 4;
    goto LABEL_57;
  }
LABEL_58:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x6E664A50u);
  if ( v7 == 4 )
    v6->IoStatus.Status = v11;
  return v7;
}

```

## disassembly

```asm
0x14002d988  mov     rax, rsp
0x14002d98b  mov     [rax+20h], r9
0x14002d98f  mov     [rax+18h], r8d
0x14002d993  mov     [rax+10h], rdx
0x14002d997  mov     [rax+8], rcx
0x14002d99b  push    rbp
0x14002d99c  push    rbx
0x14002d99d  push    rsi
0x14002d99e  push    rdi
0x14002d99f  push    r12
0x14002d9a1  push    r13
0x14002d9a3  push    r14
0x14002d9a5  push    r15
0x14002d9a7  lea     rbp, [rax-5Fh]
0x14002d9ab  sub     rsp, 0A8h
0x14002d9b2  mov     rdi, rdx
0x14002d9b5  lea     r9, [rbp+57h+P]
0x14002d9b9  mov     rdx, [rdx+18h]; Instance
0x14002d9bd  lea     r8, [rbp+57h+var_6C]
0x14002d9c1  xor     esi, esi
0x14002d9c3  xorps   xmm0, xmm0
0x14002d9c6  xor     r13d, r13d
0x14002d9c9  mov     [rbp+57h+var_68], rsi
0x14002d9cd  mov     [rbp+57h+var_60], r13
0x14002d9d1  mov     r15, rcx
0x14002d9d4  mov     [rbp+57h+var_6C], esi
0x14002d9d7  mov     r14d, 1
0x14002d9dd  movups  xmmword ptr [rbp+57h+P], xmm0
0x14002d9e1  call    PrjfIsNameOnPathOfRoot
0x14002d9e6  mov     ebx, eax
0x14002d9e8  cmp     eax, 0C0000225h
0x14002d9ed  jz      loc_14002E137
0x14002d9f3  lea     r12, WPP_RECORDER_INITIALIZED
0x14002d9fa  mov     r15b, 80h
0x14002d9fd  lea     r10, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002da04  lea     r11, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002da0b  lea     esi, [r14+2]
0x14002da0f  cmp     eax, 0C01C0005h
0x14002da14  jnz     loc_14002DAFD
0x14002da1a  mov     [rbp+57h+var_70], r14b
0x14002da1e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14002da25  mov     dl, byte ptr cs:xmmword_14001A3D0+8
0x14002da2b  setnz   r8b
0x14002da2f  and     dl, r15b
0x14002da32  jnz     short loc_14002DA39
0x14002da34  test    r8b, r8b
0x14002da37  jz      short loc_14002DA8F
0x14002da39  mov     rax, [rdi+20h]
0x14002da3d  mov     ecx, 307h
0x14002da42  mov     r9, cs:WPP_GLOBAL_Control
0x14002da49  add     rax, 58h ; 'X'
0x14002da4d  mov     [rsp+0E0h+var_90], rax
0x14002da52  mov     dword ptr [rsp+0E0h+var_98], 82h
0x14002da5a  mov     qword ptr [rsp+0E0h+var_A0], r10
0x14002da5f  mov     r9, [r9+40h]
0x14002da63  mov     qword ptr [rsp+0E0h+var_A8], r11
0x14002da68  mov     word ptr [rsp+0E0h+var_B0], 0Ah
0x14002da6f  mov     [rsp+0E0h+var_B8], 7
0x14002da77  mov     byte ptr [rsp+0E0h+var_C0], sil
0x14002da7c  call    WPP_RECORDER_AND_TRACE_SF_sDZ
0x14002da81  lea     r10, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002da88  lea     r11, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002da8f  mov     rax, [rbp+57h+CallbackData]
0x14002da93  mov     rax, [rax+10h]
0x14002da97  mov     rdi, [rax+30h]
0x14002da9b  test    rdi, rdi
0x14002da9e  jnz     loc_14002DB8C
0x14002daa4  mov     r9d, 0C0000206h
0x14002daaa  mov     ebx, r9d
0x14002daad  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14002dab4  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14002daba  setnz   r8b
0x14002dabe  and     dl, r15b
0x14002dac1  jnz     short loc_14002DACC
0x14002dac3  test    r8b, r8b
0x14002dac6  jz      loc_14002DB81
0x14002dacc  mov     rax, [rbp+57h+arg_8]
0x14002dad0  mov     rax, [rax+20h]
0x14002dad4  add     rax, 58h ; 'X'
0x14002dad8  mov     [rsp+0E0h+var_88], rax
0x14002dadd  mov     dword ptr [rsp+0E0h+var_90], r9d
0x14002dae2  mov     dword ptr [rsp+0E0h+var_98], 98h
0x14002daea  mov     qword ptr [rsp+0E0h+var_A0], r10
0x14002daef  mov     qword ptr [rsp+0E0h+var_A8], r11
0x14002daf4  mov     word ptr [rsp+0E0h+var_B0], 0Ch
0x14002dafb  jmp     short loc_14002DB5F
0x14002dafd  mov     [rbp+57h+var_70], r13b
0x14002db01  test    ebx, ebx
0x14002db03  jns     short loc_14002DA8F
0x14002db05  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14002db0b  lea     r12, WPP_RECORDER_INITIALIZED
0x14002db12  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14002db19  setnz   r8b
0x14002db1d  and     dl, r15b
0x14002db20  jnz     short loc_14002DB27
0x14002db22  test    r8b, r8b
0x14002db25  jz      short loc_14002DB81
0x14002db27  mov     rax, [rdi+20h]
0x14002db2b  lea     r10, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002db32  add     rax, 58h ; 'X'
0x14002db36  mov     [rsp+0E0h+var_88], rax
0x14002db3b  mov     dword ptr [rsp+0E0h+var_90], ebx
0x14002db3f  mov     dword ptr [rsp+0E0h+var_98], 89h
0x14002db47  mov     qword ptr [rsp+0E0h+var_A0], r10
0x14002db4c  lea     r10, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002db53  mov     qword ptr [rsp+0E0h+var_A8], r10
0x14002db58  mov     word ptr [rsp+0E0h+var_B0], 0Bh
0x14002db5f  mov     r9, cs:WPP_GLOBAL_Control
0x14002db66  mov     ecx, 207h
0x14002db6b  mov     [rsp+0E0h+var_B8], 7
0x14002db73  mov     byte ptr [rsp+0E0h+var_C0], 2
0x14002db78  mov     r9, [r9+40h]
0x14002db7c  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14002db81  mov     r14d, 4
0x14002db87  jmp     loc_14002E12F
0x14002db8c  cmp     [rbp+57h+arg_10], 9040Ch
0x14002db93  mov     ecx, [rax+20h]; BufferLength
0x14002db96  jnz     short loc_14002DC02
0x14002db98  cmp     ecx, 20h ; ' '
0x14002db9b  jnb     short loc_14002DBF5
0x14002db9d  mov     r9d, 0C0000206h
0x14002dba3  mov     ebx, r9d
0x14002dba6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14002dbad  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14002dbb3  setnz   r8b
0x14002dbb7  and     dl, r15b
0x14002dbba  jnz     short loc_14002DBC1
0x14002dbbc  test    r8b, r8b
0x14002dbbf  jz      short loc_14002DB81
0x14002dbc1  mov     rax, [rbp+57h+arg_8]
0x14002dbc5  mov     rax, [rax+20h]
0x14002dbc9  add     rax, 58h ; 'X'
0x14002dbcd  mov     [rsp+0E0h+var_88], rax
0x14002dbd2  mov     dword ptr [rsp+0E0h+var_90], r9d
0x14002dbd7  mov     dword ptr [rsp+0E0h+var_98], 0A7h
0x14002dbdf  mov     qword ptr [rsp+0E0h+var_A0], r10
0x14002dbe4  mov     qword ptr [rsp+0E0h+var_A8], r11
0x14002dbe9  mov     word ptr [rsp+0E0h+var_B0], 0Dh
0x14002dbf0  jmp     loc_14002DB5F
0x14002dbf5  mov     [rbp+57h+var_58], rdi
0x14002dbf9  add     rdi, 20h ; ' '
0x14002dbfd  add     ecx, 0FFFFFFE0h
0x14002dc00  jmp     short loc_14002DC06
0x14002dc02  mov     [rbp+57h+var_58], r13
0x14002dc06  mov     rdx, rdi; ReparseBuffer
0x14002dc09  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x14002dc10  nop     dword ptr [rax+rax+00h]
0x14002dc15  mov     ebx, eax
0x14002dc17  test    eax, eax
0x14002dc19  js      loc_14002DB81
0x14002dc1f  cmp     [rbp+57h+var_70], r13b
0x14002dc23  jz      loc_14002DCAF
0x14002dc29  cmp     dword ptr [rdi], 9000001Ch
0x14002dc2f  jnz     short loc_14002DCAF
0x14002dc31  mov     edi, 0C000CE05h
0x14002dc36  mov     r14d, 4
0x14002dc3c  mov     ebx, edi
0x14002dc3e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14002dc45  mov     dl, byte ptr cs:xmmword_14001A3D0+8
0x14002dc4b  setnz   r8b
0x14002dc4f  and     dl, r15b
0x14002dc52  jnz     short loc_14002DC5D
0x14002dc54  test    r8b, r8b
0x14002dc57  jz      loc_14002E12F
0x14002dc5d  mov     r9, cs:WPP_GLOBAL_Control
0x14002dc64  lea     r10, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002dc6b  mov     dword ptr [rsp+0E0h+var_90], edi
0x14002dc6f  mov     ecx, 307h
0x14002dc74  mov     dword ptr [rsp+0E0h+var_98], 0D8h
0x14002dc7c  mov     qword ptr [rsp+0E0h+var_A0], r10
0x14002dc81  lea     r10, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002dc88  mov     r9, [r9+40h]
0x14002dc8c  mov     qword ptr [rsp+0E0h+var_A8], r10
0x14002dc91  mov     word ptr [rsp+0E0h+var_B0], 0Fh
0x14002dc98  mov     [rsp+0E0h+var_B8], 7
0x14002dca0  mov     byte ptr [rsp+0E0h+var_C0], sil
0x14002dca5  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002dcaa  jmp     loc_14002E12F
0x14002dcaf  mov     r13, [rbp+57h+arg_8]
0x14002dcb3  lea     r9, [rbp+57h+var_68]
0x14002dcb7  lea     r8, [rbp+57h+var_60]
0x14002dcbb  mov     rdx, [r13+20h]; FileObject
0x14002dcbf  mov     rcx, [r13+18h]; Instance
0x14002dcc3  call    PrjfGetContextFileObject
0x14002dcc8  test    al, al
0x14002dcca  jnz     loc_14002DD7E
0x14002dcd0  cmp     dword ptr [rdi], 9000001Ch
0x14002dcd6  mov     esi, [rbp+57h+var_6C]
0x14002dcd9  jnz     loc_14002DF30
0x14002dcdf  test    esi, esi
0x14002dce1  jnz     short loc_14002DCE8
0x14002dce3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002dce8  cmp     dword ptr [rdi], 9000001Ch
0x14002dcee  jnz     loc_14002DF30
0x14002dcf4  cmp     esi, r14d
0x14002dcf7  jnz     loc_14002DF30
0x14002dcfd  mov     eax, [rdi+0Ch]
0x14002dd00  mov     r9d, 10h
0x14002dd06  test    r9b, al
0x14002dd09  jz      loc_14002DF27
0x14002dd0f  mov     edi, 0C000CE05h
0x14002dd14  lea     r14d, [r9-0Ch]
0x14002dd18  mov     ebx, edi
0x14002dd1a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14002dd21  mov     dl, byte ptr cs:xmmword_14001A3E0
0x14002dd27  setnz   r8b
0x14002dd2b  and     dl, r15b
0x14002dd2e  jnz     short loc_14002DD39
0x14002dd30  test    r8b, r8b
0x14002dd33  jz      loc_14002DEE0
0x14002dd39  mov     rax, [r13+20h]
0x14002dd3d  lea     r10, [rbp+57h+P]
0x14002dd41  mov     qword ptr [rsp+0E0h+var_80], r10
0x14002dd46  add     rax, 58h ; 'X'
0x14002dd4a  mov     [rsp+0E0h+var_88], rax
0x14002dd4f  lea     r10, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002dd56  mov     dword ptr [rsp+0E0h+var_90], edi
0x14002dd5a  mov     dword ptr [rsp+0E0h+var_98], 0FEh
0x14002dd62  mov     qword ptr [rsp+0E0h+var_A0], r10
0x14002dd67  lea     r10, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002dd6e  mov     qword ptr [rsp+0E0h+var_A8], r10
0x14002dd73  mov     word ptr [rsp+0E0h+var_B0], r9w
0x14002dd79  jmp     loc_14002DEBE
0x14002dd7e  cmp     [rbp+57h+var_6C], r14d
0x14002dd82  jnz     short loc_14002DD89
0x14002dd84  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002dd89  mov     r9d, [rdi]
0x14002dd8c  mov     ecx, 9000001Ch
0x14002dd91  cmp     r9d, ecx
0x14002dd94  jnz     loc_14002DF53
0x14002dd9a  mov     rsi, [rbp+57h+var_68]
0x14002dd9e  mov     eax, [rsi]
0x14002dda0  test    eax, eax
0x14002dda2  jnz     loc_14002DE2F
0x14002dda8  mov     ebx, 0C0000022h
0x14002ddad  lea     r14d, [rax+4]
0x14002ddb1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14002ddb8  mov     dl, byte ptr cs:xmmword_14001A3E0
0x14002ddbe  setnz   r8b
0x14002ddc2  and     dl, r15b
0x14002ddc5  jnz     short loc_14002DDCC
0x14002ddc7  test    r8b, r8b
0x14002ddca  jz      short loc_14002DE26
0x14002ddcc  mov     rax, [r13+20h]
0x14002ddd0  lea     r10, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002ddd7  mov     r9, cs:WPP_GLOBAL_Control
0x14002ddde  add     rax, 58h ; 'X'
0x14002dde2  mov     [rsp+0E0h+var_88], rax
0x14002dde7  mov     ecx, 407h
0x14002ddec  mov     dword ptr [rsp+0E0h+var_90], ebx
0x14002ddf0  mov     dword ptr [rsp+0E0h+var_98], 118h
0x14002ddf8  mov     r9, [r9+40h]
0x14002ddfc  mov     qword ptr [rsp+0E0h+var_A0], r10
0x14002de01  lea     r10, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002de08  mov     qword ptr [rsp+0E0h+var_A8], r10
0x14002de0d  mov     word ptr [rsp+0E0h+var_B0], 11h
0x14002de14  mov     [rsp+0E0h+var_B8], 7
0x14002de1c  mov     byte ptr [rsp+0E0h+var_C0], r14b
0x14002de21  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14002de26  mov     r13, [rbp+57h+var_60]
0x14002de2a  jmp     loc_14002E133
0x14002de2f  cmp     eax, r14d
0x14002de32  jnz     loc_14002DF3D
0x14002de38  mov     eax, [rdi+0Ch]
0x14002de3b  mov     r9d, 10h
0x14002de41  test    r9b, al
0x14002de44  jz      loc_14002DF3D
0x14002de4a  lea     esi, [r9-0Eh]
0x14002de4e  cmp     [rbp+57h+var_6C], esi
0x14002de51  jnz     loc_14002DF39
0x14002de57  mov     edi, 0C000CE05h
0x14002de5c  lea     r14d, [r9-0Ch]
0x14002de60  mov     ebx, edi
0x14002de62  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14002de69  mov     dl, byte ptr cs:xmmword_14001A3E0
0x14002de6f  setnz   r8b
0x14002de73  and     dl, r15b
0x14002de76  jnz     short loc_14002DE7D
0x14002de78  test    r8b, r8b
0x14002de7b  jz      short loc_14002DEE0
0x14002de7d  mov     rax, [r13+20h]
0x14002de81  lea     r10, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002de88  lea     r9, [rbp+57h+P]
0x14002de8c  add     rax, 58h ; 'X'
0x14002de90  mov     qword ptr [rsp+0E0h+var_80], r9
0x14002de95  mov     [rsp+0E0h+var_88], rax
0x14002de9a  mov     dword ptr [rsp+0E0h+var_90], edi
0x14002de9e  mov     dword ptr [rsp+0E0h+var_98], 132h
0x14002dea6  mov     qword ptr [rsp+0E0h+var_A0], r10
0x14002deab  lea     r10, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002deb2  mov     qword ptr [rsp+0E0h+var_A8], r10
0x14002deb7  mov     word ptr [rsp+0E0h+var_B0], 12h
0x14002debe  mov     r9, cs:WPP_GLOBAL_Control
0x14002dec5  mov     ecx, 407h
0x14002deca  mov     [rsp+0E0h+var_B8], 7
0x14002ded2  mov     byte ptr [rsp+0E0h+var_C0], r14b
0x14002ded7  mov     r9, [r9+40h]
0x14002dedb  call    WPP_RECORDER_AND_TRACE_SF_sDdZZ
0x14002dee0  test    cs:Microsoft_Windows_ProjFS_FilterEnableBits, 1
0x14002dee7  jz      short loc_14002DF30
  ... truncated ...
```
