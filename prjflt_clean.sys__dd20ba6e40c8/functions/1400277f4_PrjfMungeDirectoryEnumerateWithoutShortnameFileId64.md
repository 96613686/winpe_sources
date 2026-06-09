# PrjfMungeDirectoryEnumerateWithoutShortnameFileId64

- ea: `0x1400277f4`
- end: `0x140027c98`
- name: `PrjfMungeDirectoryEnumerateWithoutShortnameFileId64`
- size: `1188`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400287d4`

## callees

- `0x14000b1a0`
- `0x14000b1d0`
- `0x14000ba50`
- `0x14000d128`
- `0x140021008`
- `0x14002106c`
- `0x140021150`
- `0x140021198`
- `0x1400277f4`

## pseudocode

```c
__int64 __fastcall PrjfMungeDirectoryEnumerateWithoutShortnameFileId64(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        unsigned int a6,
        char a7,
        _QWORD *a8,
        unsigned int *a9)
{
  char v9; // r12
  __int64 v10; // rdi
  char v11; // r15
  int v12; // esi
  unsigned int v13; // r14d
  unsigned int v14; // ebx
  unsigned int v15; // r13d
  unsigned int v16; // r12d
  __int64 v17; // rdx
  unsigned int *v18; // r15
  unsigned int ULongFromUser; // eax
  unsigned int v20; // eax
  void *v21; // rdx
  void *v22; // rcx
  unsigned int v23; // r13d
  __int64 v24; // rdx
  __int64 v25; // rdx
  unsigned int *v26; // rcx
  unsigned int v27; // eax
  unsigned int *v28; // r15
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // rdx
  _QWORD *v32; // rcx
  unsigned int v33; // eax
  unsigned int *v34; // rcx
  void *v35; // rdx
  void *v36; // rcx
  int v37; // eax
  unsigned int v39; // [rsp+C0h] [rbp+8h]
  char v40; // [rsp+D8h] [rbp+20h]

  v40 = a4;
  v9 = a4;
  v10 = a3;
  v11 = a2;
  v12 = a1;
  v13 = 0;
  v14 = 0;
  if ( (_DWORD)a1 != 38 && (_DWORD)a1 != 78 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  if ( v12 != 38 )
  {
    if ( v12 == 78 )
    {
      v15 = *(_DWORD *)(v10 + 60);
      v16 = v15 + 80;
      if ( a6 >= v15 + 80 || a6 >= 0x50 && v11 )
      {
        if ( v15 >= a6 - 80 )
          v15 = a6 - 80;
        if ( a7 )
          RtlCopyToUser(a5, (void *)v10, 0x50u);
        else
          RtlCopyVolatileMemory(a5, (const void *)v10, 0x50u);
        if ( *(_DWORD *)(v10 + 68) == -1879048164 )
        {
          v17 = *(_DWORD *)(v10 + 56) & 0xFFFFE9FF;
          if ( (*(_DWORD *)(v10 + 56) & 0xFFFFE9FF) == 0 )
            v17 = 128;
          if ( a7 )
            RtlWriteULongToUser(a5 + 14, v17);
          else
            a5[14] = v17;
          if ( a7 )
            RtlWriteULongToUser(a5 + 17, 0);
          else
            a5[17] = 0;
        }
        if ( v40 )
        {
          v18 = a5 + 14;
          if ( a7 )
            ULongFromUser = RtlReadULongFromUser(a5 + 14);
          else
            ULongFromUser = *v18;
          v20 = ULongFromUser | 0x440000;
          if ( a7 )
            RtlWriteULongToUser(a5 + 14, v20);
          else
            *v18 = v20;
          if ( a7 )
            RtlWriteULong64ToUser(a5 + 12, 0);
          else
            *((_QWORD *)a5 + 6) = 0;
          if ( a7 )
            RtlWriteULong64ToUser(a5 + 18, -1);
          else
            *((_QWORD *)a5 + 9) = -1;
        }
        v21 = (void *)(v10 + 80);
        v22 = a5 + 20;
        if ( a7 )
          RtlCopyToUser(v22, v21, v15);
        else
          RtlCopyVolatileMemory(v22, v21, v15);
        if ( a7 )
          RtlWriteULongToUser(a5, 0);
        else
          *a5 = 0;
        *a8 = a5;
        v14 = v15 + 80;
        if ( v15 + 80 < v16 )
          v13 = -2147483643;
      }
    }
    else
    {
      if ( (BYTE10(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = BYTE10(xmmword_14001A3D0) & 4;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          786,
          a2,
          a3,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          3,
          18,
          14,
          (__int64)&WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
          68,
          v12);
      }
      MicrosoftTelemetryAssertTriggeredMsgKM("Unsupported FileInformationClass");
      v13 = -1073741637;
    }
    goto LABEL_101;
  }
  v23 = *(_DWORD *)(v10 + 60);
  v39 = v23 + 80;
  if ( a6 < v23 + 80 && (a6 < 0x50 || !v11) )
    goto LABEL_101;
  if ( v23 >= a6 - 80 )
    v23 = a6 - 80;
  if ( a7 )
    RtlCopyToUser(a5, (void *)v10, 0x38u);
  else
    RtlCopyVolatileMemory(a5, (const void *)v10, 0x38u);
  v24 = *(unsigned int *)(v10 + 56);
  if ( *(_DWORD *)(v10 + 68) == -1879048164 )
  {
    v25 = (unsigned int)v24 & 0xFFFFE9FF;
    if ( !(_DWORD)v25 )
      v25 = 128;
    if ( a7 )
      RtlWriteULongToUser(a5 + 14, v25);
    else
      a5[14] = v25;
    v26 = a5 + 16;
    goto LABEL_63;
  }
  if ( a7 )
    RtlWriteULongToUser(a5 + 14, v24);
  else
    a5[14] = v24;
  v26 = a5 + 16;
  if ( (*(_DWORD *)(v10 + 56) & 0x400) == 0 )
  {
LABEL_63:
    v27 = *(_DWORD *)(v10 + 64);
    goto LABEL_64;
  }
  v27 = *(_DWORD *)(v10 + 68);
LABEL_64:
  if ( a7 )
    RtlWriteULongToUser(v26, v27);
  else
    *v26 = v27;
  if ( !v9 )
  {
    v32 = a5 + 18;
    if ( !a7 )
    {
      *v32 = *(_QWORD *)(v10 + 72);
      goto LABEL_89;
    }
    v31 = *(_QWORD *)(v10 + 72);
    goto LABEL_87;
  }
  v28 = a5 + 14;
  if ( a7 )
    v29 = RtlReadULongFromUser(a5 + 14);
  else
    v29 = *v28;
  v30 = v29 | 0x440000;
  if ( a7 )
    RtlWriteULongToUser(a5 + 14, v30);
  else
    *v28 = v30;
  if ( a7 )
    RtlWriteULong64ToUser(a5 + 12, 0);
  else
    *((_QWORD *)a5 + 6) = 0;
  if ( a7 )
  {
    v31 = -1;
    v32 = a5 + 18;
LABEL_87:
    RtlWriteULong64ToUser(v32, v31);
    goto LABEL_89;
  }
  *((_QWORD *)a5 + 9) = -1;
LABEL_89:
  v33 = *(_DWORD *)(v10 + 60);
  v34 = a5 + 15;
  if ( a7 )
    RtlWriteULongToUser(v34, v33);
  else
    *v34 = v33;
  v35 = (void *)(v10 + 80);
  v36 = a5 + 20;
  if ( a7 )
    RtlCopyToUser(v36, v35, v23);
  else
    RtlCopyVolatileMemory(v36, v35, v23);
  if ( a7 )
    RtlWriteULongToUser(a5, 0);
  else
    *a5 = 0;
  *a8 = a5;
  v14 = v23 + 80;
  v37 = 0;
  if ( v23 + 80 < v39 )
    v37 = -2147483643;
  v13 = v37;
LABEL_101:
  *a9 = v14;
  return v13;
}

```

## disassembly

```asm
0x1400277f4  mov     rax, rsp
0x1400277f7  mov     [rax+10h], rbx
0x1400277fb  mov     [rax+18h], rsi
0x1400277ff  mov     [rax+20h], r9b
0x140027803  push    rdi
0x140027804  push    r12
0x140027806  push    r13
0x140027808  push    r14
0x14002780a  push    r15
0x14002780c  sub     rsp, 90h
0x140027813  mov     r12b, r9b
0x140027816  mov     rdi, r8
0x140027819  mov     r15b, dl
0x14002781c  mov     esi, ecx
0x14002781e  mov     byte ptr [rax-58h], 0
0x140027822  xor     r14d, r14d
0x140027825  xor     ebx, ebx
0x140027827  cmp     ecx, 26h ; '&'
0x14002782a  jz      short loc_140027837
0x14002782c  cmp     ecx, 4Eh ; 'N'
0x14002782f  jz      short loc_140027837
0x140027831  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140027836  nop
0x140027837  cmp     esi, 26h ; '&'
0x14002783a  jz      loc_140027A70
0x140027840  cmp     esi, 4Eh ; 'N'
0x140027843  jz      loc_1400278D9
0x140027849  mov     dl, byte ptr cs:xmmword_14001A3D0+0Ah
0x14002784f  lea     rcx, WPP_RECORDER_INITIALIZED
0x140027856  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002785d  setnz   r8b
0x140027861  and     dl, 4
0x140027864  jnz     short loc_14002786B
0x140027866  test    r8b, r8b
0x140027869  jz      short loc_1400278BD
0x14002786b  mov     ecx, 312h
0x140027870  mov     r9d, 0Eh
0x140027876  mov     [rsp+0B8h+var_68], esi
0x14002787a  mov     [rsp+0B8h+var_70], 344h
0x140027882  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140027889  mov     [rsp+0B8h+var_78], rax
0x14002788e  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x140027895  mov     [rsp+0B8h+var_80], rax
0x14002789a  mov     [rsp+0B8h+var_88], r9w
0x1400278a0  mov     [rsp+0B8h+var_90], 12h
0x1400278a8  mov     [rsp+0B8h+var_98], 3
0x1400278ad  mov     r9, cs:WPP_GLOBAL_Control
0x1400278b4  mov     r9, [r9+40h]
0x1400278b8  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400278bd  lea     rcx, aUnsupportedFil; "Unsupported FileInformationClass"
0x1400278c4  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400278c9  mov     r14d, 0C00000BBh
0x1400278cf  mov     [rsp+0B8h+var_40], r14d
0x1400278d4  jmp     loc_140027C60
0x1400278d9  mov     r13d, [rdi+3Ch]
0x1400278dd  lea     r12d, [r13+50h]
0x1400278e1  mov     eax, [rsp+0B8h+arg_28]
0x1400278e8  cmp     eax, r12d
0x1400278eb  jnb     short loc_1400278FF
0x1400278ed  cmp     eax, 50h ; 'P'
0x1400278f0  jb      loc_140027C60
0x1400278f6  test    r15b, r15b
0x1400278f9  jz      loc_140027C60
0x1400278ff  add     eax, 0FFFFFFB0h
0x140027902  cmp     r13d, eax
0x140027905  cmovnb  r13d, eax
0x140027909  mov     [rsp+0B8h+var_58], 1
0x14002790e  mov     sil, [rsp+0B8h+arg_30]
0x140027916  mov     r8d, 50h ; 'P'; Size
0x14002791c  mov     rdx, rdi; Src
0x14002791f  mov     rbx, [rsp+0B8h+arg_20]
0x140027927  mov     rcx, rbx; void *
0x14002792a  test    sil, sil
0x14002792d  jz      short loc_140027936
0x14002792f  call    RtlCopyToUser
0x140027934  jmp     short loc_14002793B
0x140027936  call    RtlCopyVolatileMemory
0x14002793b  cmp     dword ptr [rdi+44h], 9000001Ch
0x140027942  jnz     short loc_1400279A2
0x140027944  mov     edx, [rdi+38h]
0x140027947  mov     [rsp+0B8h+var_50], edx
0x14002794b  mov     eax, edx
0x14002794d  btr     eax, 0Ah
0x140027951  mov     [rsp+0B8h+var_50], eax
0x140027955  mov     eax, edx
0x140027957  and     eax, 0FFFFEBFFh
0x14002795c  mov     [rsp+0B8h+var_50], eax
0x140027960  and     edx, 0FFFFE9FFh
0x140027966  mov     [rsp+0B8h+var_50], edx
0x14002796a  mov     eax, 80h
0x14002796f  cmovz   edx, eax
0x140027972  mov     [rsp+0B8h+var_50], edx
0x140027976  test    sil, sil
0x140027979  jz      short loc_140027986
0x14002797b  lea     rcx, [rbx+38h]
0x14002797f  call    RtlWriteULongToUser
0x140027984  jmp     short loc_140027989
0x140027986  mov     [rbx+38h], edx
0x140027989  test    sil, sil
0x14002798c  jz      short loc_14002799B
0x14002798e  xor     edx, edx
0x140027990  lea     rcx, [rbx+44h]
0x140027994  call    RtlWriteULongToUser
0x140027999  jmp     short loc_1400279A2
0x14002799b  mov     dword ptr [rbx+44h], 0
0x1400279a2  cmp     [rsp+0B8h+arg_18], 0
0x1400279aa  jz      short loc_140027A11
0x1400279ac  lea     r15, [rbx+38h]
0x1400279b0  test    sil, sil
0x1400279b3  jz      short loc_1400279BF
0x1400279b5  mov     rcx, r15
0x1400279b8  call    RtlReadULongFromUser
0x1400279bd  jmp     short loc_1400279C2
0x1400279bf  mov     eax, [r15]
0x1400279c2  or      eax, 440000h
0x1400279c7  test    sil, sil
0x1400279ca  jz      short loc_1400279D8
0x1400279cc  mov     edx, eax
0x1400279ce  mov     rcx, r15
0x1400279d1  call    RtlWriteULongToUser
0x1400279d6  jmp     short loc_1400279DB
0x1400279d8  mov     [r15], eax
0x1400279db  test    sil, sil
0x1400279de  jz      short loc_1400279ED
0x1400279e0  xor     edx, edx
0x1400279e2  lea     rcx, [rbx+30h]
0x1400279e6  call    RtlWriteULong64ToUser
0x1400279eb  jmp     short loc_1400279F5
0x1400279ed  mov     qword ptr [rbx+30h], 0
0x1400279f5  test    sil, sil
0x1400279f8  jz      short loc_140027A09
0x1400279fa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400279fe  lea     rcx, [rbx+48h]
0x140027a02  call    RtlWriteULong64ToUser
0x140027a07  jmp     short loc_140027A11
0x140027a09  mov     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x140027a11  lea     rdx, [rdi+50h]; Src
0x140027a15  lea     rcx, [rbx+50h]; void *
0x140027a19  mov     r8d, r13d; Size
0x140027a1c  test    sil, sil
0x140027a1f  jz      short loc_140027A28
0x140027a21  call    RtlCopyToUser
0x140027a26  jmp     short loc_140027A2D
0x140027a28  call    RtlCopyVolatileMemory
0x140027a2d  test    sil, sil
0x140027a30  jz      short loc_140027A3E
0x140027a32  xor     edx, edx
0x140027a34  mov     rcx, rbx
0x140027a37  call    RtlWriteULongToUser
0x140027a3c  jmp     short loc_140027A44
0x140027a3e  mov     dword ptr [rbx], 0
0x140027a44  mov     rax, [rsp+0B8h+arg_38]
0x140027a4c  mov     [rax], rbx
0x140027a4f  mov     [rsp+0B8h+var_58], 0
0x140027a54  lea     ebx, [r13+50h]
0x140027a58  mov     [rsp+0B8h+var_3C], ebx
0x140027a5c  cmp     ebx, r12d
0x140027a5f  jnb     loc_140027C60
0x140027a65  mov     r14d, 80000005h
0x140027a6b  jmp     loc_1400278CF
0x140027a70  mov     r13d, [rdi+3Ch]
0x140027a74  lea     ecx, [r13+50h]
0x140027a78  mov     [rsp+0B8h+arg_0], ecx
0x140027a7f  mov     eax, [rsp+0B8h+arg_28]
0x140027a86  cmp     eax, ecx
0x140027a88  jnb     short loc_140027A9C
0x140027a8a  cmp     eax, 50h ; 'P'
0x140027a8d  jb      loc_140027C60
0x140027a93  test    r15b, r15b
0x140027a96  jz      loc_140027C60
0x140027a9c  add     eax, 0FFFFFFB0h
0x140027a9f  cmp     r13d, eax
0x140027aa2  cmovnb  r13d, eax
0x140027aa6  mov     [rsp+0B8h+var_58], 1
0x140027aab  mov     sil, [rsp+0B8h+arg_30]
0x140027ab3  mov     r8d, 38h ; '8'; Size
0x140027ab9  mov     rdx, rdi; Src
0x140027abc  mov     rbx, [rsp+0B8h+arg_20]
0x140027ac4  mov     rcx, rbx; void *
0x140027ac7  test    sil, sil
0x140027aca  jz      short loc_140027AD3
0x140027acc  call    RtlCopyToUser
0x140027ad1  jmp     short loc_140027AD8
0x140027ad3  call    RtlCopyVolatileMemory
0x140027ad8  mov     edx, [rdi+38h]
0x140027adb  cmp     dword ptr [rdi+44h], 9000001Ch
0x140027ae2  jnz     short loc_140027B3B
0x140027ae4  mov     [rsp+0B8h+var_48], edx
0x140027ae8  mov     eax, edx
0x140027aea  btr     eax, 0Ah
0x140027aee  mov     [rsp+0B8h+var_48], eax
0x140027af2  mov     eax, edx
0x140027af4  and     eax, 0FFFFEBFFh
0x140027af9  mov     [rsp+0B8h+var_48], eax
0x140027afd  and     edx, 0FFFFE9FFh
0x140027b03  mov     [rsp+0B8h+var_48], edx
0x140027b07  mov     eax, 80h
0x140027b0c  cmovz   edx, eax
0x140027b0f  mov     [rsp+0B8h+var_48], edx
0x140027b13  test    sil, sil
0x140027b16  jz      short loc_140027B23
0x140027b18  lea     rcx, [rbx+38h]
0x140027b1c  call    RtlWriteULongToUser
0x140027b21  jmp     short loc_140027B26
0x140027b23  mov     [rbx+38h], edx
0x140027b26  lea     rcx, [rbx+40h]
0x140027b2a  mov     eax, [rdi+40h]
0x140027b2d  test    sil, sil
0x140027b30  jz      short loc_140027B60
0x140027b32  mov     edx, eax
0x140027b34  call    RtlWriteULongToUser
0x140027b39  jmp     short loc_140027B62
0x140027b3b  test    sil, sil
0x140027b3e  jz      short loc_140027B4B
0x140027b40  lea     rcx, [rbx+38h]
0x140027b44  call    RtlWriteULongToUser
0x140027b49  jmp     short loc_140027B4E
0x140027b4b  mov     [rbx+38h], edx
0x140027b4e  lea     rcx, [rbx+40h]
0x140027b52  test    dword ptr [rdi+38h], 400h
0x140027b59  jz      short loc_140027B2A
0x140027b5b  mov     eax, [rdi+44h]
0x140027b5e  jmp     short loc_140027B2D
0x140027b60  mov     [rcx], eax
0x140027b62  test    r12b, r12b
0x140027b65  jz      short loc_140027BC9
0x140027b67  lea     r15, [rbx+38h]
0x140027b6b  test    sil, sil
0x140027b6e  jz      short loc_140027B7A
0x140027b70  mov     rcx, r15
0x140027b73  call    RtlReadULongFromUser
0x140027b78  jmp     short loc_140027B7D
0x140027b7a  mov     eax, [r15]
0x140027b7d  or      eax, 440000h
0x140027b82  test    sil, sil
0x140027b85  jz      short loc_140027B93
0x140027b87  mov     edx, eax
0x140027b89  mov     rcx, r15
0x140027b8c  call    RtlWriteULongToUser
0x140027b91  jmp     short loc_140027B96
0x140027b93  mov     [r15], eax
0x140027b96  test    sil, sil
0x140027b99  jz      short loc_140027BA8
0x140027b9b  xor     edx, edx
0x140027b9d  lea     rcx, [rbx+30h]
0x140027ba1  call    RtlWriteULong64ToUser
0x140027ba6  jmp     short loc_140027BB0
0x140027ba8  mov     qword ptr [rbx+30h], 0
0x140027bb0  test    sil, sil
0x140027bb3  jz      short loc_140027BBF
0x140027bb5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140027bb9  lea     rcx, [rbx+48h]
0x140027bbd  jmp     short loc_140027BD9
0x140027bbf  mov     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x140027bc7  jmp     short loc_140027BE3
0x140027bc9  mov     rax, [rdi+48h]
0x140027bcd  lea     rcx, [rbx+48h]
0x140027bd1  test    sil, sil
0x140027bd4  jz      short loc_140027BE0
0x140027bd6  mov     rdx, rax
0x140027bd9  call    RtlWriteULong64ToUser
0x140027bde  jmp     short loc_140027BE3
0x140027be0  mov     [rcx], rax
0x140027be3  mov     eax, [rdi+3Ch]
0x140027be6  lea     rcx, [rbx+3Ch]
0x140027bea  test    sil, sil
0x140027bed  jz      short loc_140027BF8
0x140027bef  mov     edx, eax
0x140027bf1  call    RtlWriteULongToUser
0x140027bf6  jmp     short loc_140027BFA
0x140027bf8  mov     [rcx], eax
0x140027bfa  lea     rdx, [rdi+50h]; Src
0x140027bfe  lea     rcx, [rbx+50h]; void *
0x140027c02  mov     r8d, r13d; Size
0x140027c05  test    sil, sil
0x140027c08  jz      short loc_140027C11
0x140027c0a  call    RtlCopyToUser
0x140027c0f  jmp     short loc_140027C16
0x140027c11  call    RtlCopyVolatileMemory
0x140027c16  test    sil, sil
0x140027c19  jz      short loc_140027C27
0x140027c1b  xor     edx, edx
0x140027c1d  mov     rcx, rbx
0x140027c20  call    RtlWriteULongToUser
0x140027c25  jmp     short loc_140027C2D
0x140027c27  mov     dword ptr [rbx], 0
0x140027c2d  mov     rax, [rsp+0B8h+arg_38]
0x140027c35  mov     [rax], rbx
0x140027c38  mov     [rsp+0B8h+var_58], 0
0x140027c3d  lea     ebx, [r13+50h]
0x140027c41  mov     [rsp+0B8h+var_3C], ebx
0x140027c45  mov     eax, r14d
0x140027c48  mov     r14d, 80000005h
0x140027c4e  cmp     ebx, [rsp+0B8h+arg_0]
0x140027c55  cmovb   eax, r14d
0x140027c59  mov     r14d, eax
0x140027c5c  mov     [rsp+0B8h+var_40], eax
0x140027c60  mov     rax, [rsp+0B8h+arg_40]
0x140027c68  mov     [rax], ebx
0x140027c6a  jmp     short loc_140027C77
  ... truncated ...
```
