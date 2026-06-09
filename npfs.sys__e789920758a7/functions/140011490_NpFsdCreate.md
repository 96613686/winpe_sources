# NpFsdCreate

- ea: `0x140011490`
- end: `0x140011a94`
- name: `NpFsdCreate`
- size: `1540`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x14000c734`
- `0x140011490`
- `0x140011f60`
- `0x140012730`
- `0x1400127f0`
- `0x1400131e0`
- `0x1400137d4`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140011880`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140011880`
- `ntoskrnl!ExAllocatePool2` at `0x1400115a1`
- `ntoskrnl!ExAllocatePool2` at `0x1400115a1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011677`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001181a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011968`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011677`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001181a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011968`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011693`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011836`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001197e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011a05`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011a3c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011693`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011836`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001197e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011a05`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011a3c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400116c8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400117a8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001186b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011a83`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400116c8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400117a8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001186b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011a83`
- `ntoskrnl!IofCompleteRequest` at `0x14001152f`
- `ntoskrnl!IofCompleteRequest` at `0x1400117cd`
- `ntoskrnl!IofCompleteRequest` at `0x14001152f`
- `ntoskrnl!IofCompleteRequest` at `0x1400117cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400117e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400117e2`

## pseudocode

```c
__int64 __fastcall NpFsdCreate(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v3; // r13
  __int64 v5; // r14
  KPROCESSOR_MODE v6; // r9
  __int64 v7; // r15
  bool v8; // zf
  __int64 v9; // rax
  unsigned int v10; // ecx
  struct _ACCESS_STATE *v11; // rdx
  ACCESS_MASK DesiredAccess; // r8d
  __int16 v13; // r12
  int v14; // edi
  __int64 Pool2; // rax
  PACCESS_TOKEN ClientToken; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 Prefix; // r12
  int v24; // r15d
  __int64 v25; // rax
  __int64 *v26; // rsi
  IRP *v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // r8
  __int64 v31; // r8
  __int64 v32; // r9
  int v33; // ecx
  __int64 v34; // r8
  __int64 v35; // r9
  KPROCESSOR_MODE PreviousMode[8]; // [rsp+28h] [rbp-71h]
  DWORD v37; // [rsp+50h] [rbp-49h]
  __int64 v38; // [rsp+60h] [rbp-39h]
  __int64 v39; // [rsp+68h] [rbp-31h]
  PACCESS_STATE AccessState[2]; // [rsp+70h] [rbp-29h]
  struct _UNICODE_STRING UnicodeString; // [rsp+80h] [rbp-19h] BYREF
  __int64 v42[2]; // [rsp+90h] [rbp-9h] BYREF
  int AccessStatus[20]; // [rsp+A0h] [rbp+7h] BYREF
  char v44; // [rsp+100h] [rbp+67h]
  int v45; // [rsp+108h] [rbp+6Fh] BYREF
  int v46; // [rsp+110h] [rbp+77h]
  __int64 v47; // [rsp+118h] [rbp+7Fh]

  v2 = *(_QWORD *)(a2 + 184);
  v3 = *(_QWORD *)(a1 + 64);
  UnicodeString = 0;
  v45 = 0;
  *(_OWORD *)v42 = 0;
  v5 = *(_QWORD *)(v2 + 48);
  v6 = 1;
  *(_OWORD *)AccessStatus = 0;
  v7 = *(_QWORD *)(v5 + 64);
  UnicodeString = *(struct _UNICODE_STRING *)(v5 + 88);
  v8 = (*(_BYTE *)(v2 + 2) & 1) == 0;
  v9 = *(_QWORD *)(v2 + 8);
  v10 = *(_DWORD *)(v2 + 16);
  v11 = *(struct _ACCESS_STATE **)(v9 + 8);
  DesiredAccess = *(_DWORD *)(v9 + 16);
  AccessState[0] = v11;
  v46 = *(_DWORD *)(v9 + 16);
  if ( v8 )
    v6 = *(_BYTE *)(a2 + 64);
  v13 = 0;
  v39 = *(_QWORD *)(a2 + 24);
  v44 = v6;
  if ( v7 )
  {
    if ( (*(_QWORD *)(v7 + 32) & 1) == 0 )
    {
LABEL_5:
      v14 = -1073741773;
      goto LABEL_6;
    }
    v13 = **(_WORD **)(v7 + 24);
  }
  if ( UnicodeString.Length )
  {
    if ( UnicodeString.Length == 2 && *UnicodeString.Buffer == 92 && !v7 )
    {
LABEL_14:
      *(_OWORD *)AccessState = 0;
      Pool2 = ExAllocatePool2(257, 24, 1128689742);
      if ( Pool2 )
      {
        *(_OWORD *)Pool2 = 0;
        *(_QWORD *)(Pool2 + 16) = 0;
        *(_WORD *)Pool2 = 517;
        *(_QWORD *)(v5 + 32) = Pool2 | 1;
        *(_QWORD *)(v5 + 24) = v3 + 296;
        _InterlockedIncrement((volatile signed __int32 *)(v3 + 120));
        AccessState[1] = (PACCESS_STATE)1;
      }
      else
      {
        LODWORD(AccessState[0]) = -1073741670;
      }
      *(_OWORD *)(a2 + 48) = *(_OWORD *)AccessState;
      v14 = *(_DWORD *)(a2 + 48);
      goto LABEL_6;
    }
  }
  else
  {
    if ( !v7 || v13 == 513 )
    {
      AccessState[0] = 0;
      *(_QWORD *)(v5 + 32) = 1;
      *(_QWORD *)(v5 + 24) = v3;
      _InterlockedIncrement((volatile signed __int32 *)(v3 + 120));
      AccessState[1] = (PACCESS_STATE)1;
      *(_OWORD *)(a2 + 48) = *(_OWORD *)AccessState;
      v14 = *(_DWORD *)(a2 + 48);
      goto LABEL_6;
    }
    if ( v13 == 518 )
      goto LABEL_14;
  }
  if ( (v10 & 1) != 0 )
  {
    if ( v7 )
      goto LABEL_5;
    v33 = HIBYTE(v10);
    if ( v33 == 1 )
    {
      PreviousMode[0] = v6;
      *(_OWORD *)(a2 + 48) = *(_OWORD *)NpOpenNamedPipePrefix(
                                          AccessStatus,
                                          v3,
                                          v5,
                                          v11,
                                          DesiredAccess,
                                          *(_DWORD *)PreviousMode);
      v14 = *(_DWORD *)(a2 + 48);
    }
    else
    {
      if ( (unsigned int)(v33 - 2) > 1 )
        goto LABEL_5;
      *(_OWORD *)(a2 + 48) = *(_OWORD *)NpCreateNamedPipePrefix(
                                          (int)AccessStatus,
                                          v3,
                                          v5,
                                          (int)v11,
                                          DesiredAccess,
                                          v6,
                                          v33);
      v14 = *(_DWORD *)(a2 + 48);
    }
  }
  else
  {
    if ( *(_BYTE *)(a2 + 64) == 1 )
    {
      ClientToken = v11->SubjectSecurityContext.ClientToken;
      if ( !ClientToken )
        ClientToken = v11->SubjectSecurityContext.PrimaryToken;
    }
    else
    {
      ClientToken = 0;
    }
    v14 = NpTranslateAlias(&UnicodeString, ClientToken, &v45);
    if ( v14 >= 0 )
    {
      LODWORD(v38) = 0;
      v42[1] = (__int64)v42;
      v42[0] = (__int64)v42;
      if ( !v7 )
      {
        if ( UnicodeString.Length <= 2u || *UnicodeString.Buffer != 92 )
          goto LABEL_5;
        KeEnterCriticalRegion();
        v47 = v3 + 192;
        ExAcquirePushLockExclusiveEx(v3 + 192, 0, v18, v19);
        LOBYTE(v20) = 1;
        Prefix = NpFindPrefix(v3, &UnicodeString, v20, AccessStatus);
        if ( !Prefix )
          goto LABEL_26;
        if ( *(_WORD *)Prefix == 514 )
        {
          ExAcquirePushLockExclusiveEx(Prefix + 128, 0, v21, v22);
LABEL_26:
          ExReleasePushLockExclusiveEx(v3 + 192, 0);
          v47 = v3 + 192;
LABEL_27:
          v24 = v38;
LABEL_28:
          if ( LOWORD(AccessStatus[0]) )
          {
            v14 = (Prefix == 0) - 1073741773;
            v25 = v47;
LABEL_35:
            if ( v24 )
              ExReleasePushLockExclusiveEx(v25, 0);
            if ( Prefix && *(_WORD *)Prefix == 514 )
              ExReleasePushLockExclusiveEx(Prefix + 128, 0);
            v26 = (__int64 *)v42[0];
            while ( v26 != v42 )
            {
              v27 = (IRP *)(v26 - 21);
              v26 = (__int64 *)*v26;
              IofCompleteRequest(v27, 2);
            }
            KeLeaveCriticalRegion();
            goto LABEL_6;
          }
          v25 = v47;
LABEL_30:
          if ( Prefix )
          {
            if ( *(_WORD *)Prefix == 514 )
            {
              if ( *(_DWORD *)(Prefix + 248) )
              {
                *(_OWORD *)(a2 + 48) = *(_OWORD *)NpCreateClientEnd(
                                                    AccessStatus,
                                                    **(_QWORD **)(v2 + 8),
                                                    AccessState[0],
                                                    *(_BYTE *)(a2 + 64) == 0,
                                                    v44,
                                                    *(PETHREAD *)(a2 + 152),
                                                    v39,
                                                    v37,
                                                    (__int64)v42);
                v14 = *(_DWORD *)(a2 + 48);
              }
              else
              {
                v14 = -1073741772;
              }
            }
            else if ( *(_WORD *)Prefix == 519 )
            {
              v14 = NpOpenSymlink(Prefix, a2);
            }
            v25 = v3 + 192;
          }
          else
          {
            v14 = -1073741773;
          }
          goto LABEL_35;
        }
        if ( *(_WORD *)Prefix != 519 )
        {
          Prefix = 0;
          goto LABEL_26;
        }
LABEL_73:
        v24 = 1;
        goto LABEL_28;
      }
      if ( v13 != 518 )
      {
        if ( v13 != 514 || UnicodeString.Length )
          goto LABEL_5;
        Prefix = *(_QWORD *)((*(_QWORD *)(v7 + 32) & 0xFFFFFFFFFFFFFFFCuLL) + 40);
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(Prefix + 128, 0, v34, v35);
        v24 = v38;
        v25 = v3 + 192;
        goto LABEL_30;
      }
      KeEnterCriticalRegion();
      v47 = v3 + 192;
      ExAcquirePushLockExclusiveEx(v3 + 192, 0, v28, v29);
      LOBYTE(v30) = 1;
      Prefix = NpFindPrefix(v3, &UnicodeString, v30, AccessStatus);
      if ( Prefix )
      {
        if ( *(_WORD *)Prefix == 514 )
        {
          ExAcquirePushLockExclusiveEx(Prefix + 128, 0, v31, v32);
        }
        else
        {
          if ( *(_WORD *)Prefix == 519 )
            goto LABEL_73;
          Prefix = 0;
        }
      }
      ExReleasePushLockExclusiveEx(v3 + 192, 0);
      goto LABEL_27;
    }
  }
LABEL_6:
  *(_DWORD *)(a2 + 48) = v14;
  IofCompleteRequest((PIRP)a2, 2);
  if ( v45 )
    RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140011490  push    rbp
0x140011492  push    rbx
0x140011493  push    rsi
0x140011494  push    rdi
0x140011495  push    r12
0x140011497  push    r13
0x140011499  push    r14
0x14001149b  push    r15
0x14001149d  lea     rbp, [rsp-1Fh]
0x1400114a2  sub     rsp, 0B8h
0x1400114a9  mov     rsi, [rdx+0B8h]
0x1400114b0  xorps   xmm0, xmm0
0x1400114b3  mov     r13, [rcx+40h]
0x1400114b7  xor     r10d, r10d
0x1400114ba  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x1400114be  mov     rbx, rdx
0x1400114c1  mov     [rbp+57h+arg_8], r10d
0x1400114c5  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1400114c9  mov     r14, [rsi+30h]
0x1400114cd  mov     r9b, 1
0x1400114d0  xorps   xmm1, xmm1
0x1400114d3  movups  xmmword ptr [rbp+57h+AccessStatus], xmm1
0x1400114d7  movups  xmm0, xmmword ptr [r14+58h]
0x1400114dc  mov     r15, [r14+40h]
0x1400114e0  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x1400114e4  test    byte ptr [rsi+2], 1
0x1400114e8  mov     rax, [rsi+8]
0x1400114ec  mov     ecx, [rsi+10h]
0x1400114ef  mov     rdx, [rax+8]
0x1400114f3  mov     r8d, [rax+10h]
0x1400114f7  mov     [rbp+57h+AccessState], rdx
0x1400114fb  mov     [rbp+57h+arg_10], r8d
0x1400114ff  jnz     short loc_140011506
0x140011501  movzx   r9d, byte ptr [rbx+40h]
0x140011506  mov     rax, [rbx+18h]
0x14001150a  mov     r12d, r10d
0x14001150d  mov     [rbp+57h+var_88], rax
0x140011511  mov     [rbp+57h+arg_0], r9b
0x140011515  test    r15, r15
0x140011518  jz      short loc_140011564
0x14001151a  mov     rax, [r15+20h]
0x14001151e  test    al, 1
0x140011520  jnz     short loc_14001155C
0x140011522  mov     edi, 0C0000033h
0x140011527  mov     dl, 2; PriorityBoost
0x140011529  mov     [rbx+30h], edi
0x14001152c  mov     rcx, rbx; Irp
0x14001152f  call    cs:__imp_IofCompleteRequest
0x140011536  nop     dword ptr [rax+rax+00h]
0x14001153b  cmp     [rbp+57h+arg_8], 0
0x14001153f  jnz     loc_14001187C
0x140011545  mov     eax, edi
0x140011547  add     rsp, 0B8h
0x14001154e  pop     r15
0x140011550  pop     r14
0x140011552  pop     r13
0x140011554  pop     r12
0x140011556  pop     rdi
0x140011557  pop     rsi
0x140011558  pop     rbx
0x140011559  pop     rbp
0x14001155a  retn
0x14001155c  mov     rax, [r15+18h]
0x140011560  movzx   r12d, word ptr [rax]
0x140011564  movzx   eax, [rbp+57h+UnicodeString.Length]
0x140011568  test    ax, ax
0x14001156b  jz      loc_140011899
0x140011571  cmp     ax, 2
0x140011575  jnz     loc_1400115FB
0x14001157b  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x14001157f  cmp     word ptr [rax], 5Ch ; '\'
0x140011583  jnz     short loc_140011604
0x140011585  test    r15, r15
0x140011588  jnz     short loc_140011604
0x14001158a  xorps   xmm0, xmm0
0x14001158d  mov     edx, 18h
0x140011592  mov     ecx, 101h
0x140011597  mov     r8d, 4346704Eh
0x14001159d  movups  xmmword ptr [rbp+57h+AccessState], xmm0
0x1400115a1  call    cs:__imp_ExAllocatePool2
0x1400115a8  nop     dword ptr [rax+rax+00h]
0x1400115ad  mov     rcx, rax
0x1400115b0  test    rax, rax
0x1400115b3  jz      loc_1400119E5
0x1400115b9  xor     eax, eax
0x1400115bb  xorps   xmm0, xmm0
0x1400115be  movups  xmmword ptr [rcx], xmm0
0x1400115c1  mov     [rcx+10h], rax
0x1400115c5  lea     rax, [r13+128h]
0x1400115cc  mov     word ptr [rcx], 205h
0x1400115d1  or      rcx, 1
0x1400115d5  mov     [r14+20h], rcx
0x1400115d9  mov     [r14+18h], rax
0x1400115dd  lock inc dword ptr [r13+78h]
0x1400115e2  mov     eax, 1
0x1400115e7  mov     [rbp+57h+AccessState+8], rax
0x1400115eb  movups  xmm0, xmmword ptr [rbp+57h+AccessState]
0x1400115ef  movups  xmmword ptr [rbx+30h], xmm0
0x1400115f3  mov     edi, [rbx+30h]
0x1400115f6  jmp     loc_140011527
0x1400115fb  test    ax, ax
0x1400115fe  jz      loc_1400118CD
0x140011604  test    cl, 1
0x140011607  jnz     loc_1400118E1
0x14001160d  cmp     byte ptr [rbx+40h], 1
0x140011611  jnz     loc_140011891
0x140011617  mov     rax, [rdx+20h]
0x14001161b  test    rax, rax
0x14001161e  jnz     short loc_140011624
0x140011620  mov     rax, [rdx+30h]
0x140011624  lea     r8, [rbp+57h+arg_8]
0x140011628  mov     rdx, rax
0x14001162b  lea     rcx, [rbp+57h+UnicodeString]
0x14001162f  call    NpTranslateAlias
0x140011634  mov     edi, eax
0x140011636  test    eax, eax
0x140011638  js      loc_140011527
0x14001163e  mov     dword ptr [rbp+57h+var_90], 0
0x140011645  lea     rax, [rbp+57h+var_60]
0x140011649  mov     [rbp+57h+var_60+8], rax
0x14001164d  lea     rax, [rbp+57h+var_60]
0x140011651  mov     [rbp+57h+var_60], rax
0x140011655  test    r15, r15
0x140011658  jnz     loc_14001180B
0x14001165e  cmp     [rbp+57h+UnicodeString.Length], 2
0x140011663  jbe     loc_140011522
0x140011669  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x14001166d  cmp     word ptr [rax], 5Ch ; '\'
0x140011671  jnz     loc_140011522
0x140011677  call    cs:__imp_KeEnterCriticalRegion
0x14001167e  nop     dword ptr [rax+rax+00h]
0x140011683  lea     r15, [r13+0C0h]
0x14001168a  xor     edx, edx
0x14001168c  mov     rcx, r15
0x14001168f  mov     [rbp+57h+arg_18], r15
0x140011693  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001169a  nop     dword ptr [rax+rax+00h]
0x14001169f  lea     r9, [rbp+57h+AccessStatus]
0x1400116a3  mov     r8b, 1
0x1400116a6  lea     rdx, [rbp+57h+UnicodeString]
0x1400116aa  mov     rcx, r13
0x1400116ad  call    NpFindPrefix
0x1400116b2  mov     r12, rax
0x1400116b5  mov     eax, 202h
0x1400116ba  test    r12, r12
0x1400116bd  jnz     loc_140011A28
0x1400116c3  xor     edx, edx
0x1400116c5  mov     rcx, r15
0x1400116c8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400116cf  nop     dword ptr [rax+rax+00h]
0x1400116d4  mov     [rbp+57h+arg_18], r15
0x1400116d8  mov     r15, [rbp+57h+var_90]
0x1400116dc  cmp     word ptr [rbp+57h+AccessStatus], 0
0x1400116e1  jnz     loc_1400117F3
0x1400116e7  mov     rax, [rbp+57h+arg_18]
0x1400116eb  test    r12, r12
0x1400116ee  jz      loc_140011A74
0x1400116f4  movzx   ecx, word ptr [r12]
0x1400116f9  mov     eax, 202h
0x1400116fe  cmp     cx, ax
0x140011701  jnz     loc_14001199A
0x140011707  cmp     dword ptr [r12+0F8h], 0
0x140011710  jz      loc_140011A6A
0x140011716  mov     rdx, [rsi+8]
0x14001171a  lea     rax, [rbp+57h+var_60]
0x14001171e  cmp     byte ptr [rbx+40h], 0
0x140011722  mov     r8, r14
0x140011725  mov     r9d, [rbp+57h+arg_10]
0x140011729  mov     [rsp+0F0h+var_98], rax; __int64
0x14001172e  setz    cl
0x140011731  mov     rax, [rbp+57h+var_88]
0x140011735  and     r9d, 0FFFFFFFBh
0x140011739  mov     [rsp+0F0h+var_A8], rax; __int64
0x14001173e  mov     rax, [rbx+98h]
0x140011745  mov     [rsp+0F0h+Thread], rax; Thread
0x14001174a  movzx   eax, [rbp+57h+arg_0]
0x14001174e  mov     [rsp+0F0h+var_B8], al; char
0x140011752  mov     rax, [rbp+57h+AccessState]
0x140011756  mov     [rsp+0F0h+var_C0], cl; char
0x14001175a  lea     rcx, [rbp+57h+AccessStatus]; AccessStatus
0x14001175e  mov     qword ptr [rsp+0F0h+PreviousMode], rax; AccessState
0x140011763  mov     rax, [rdx]
0x140011766  mov     rdx, r12
0x140011769  mov     qword ptr [rsp+0F0h+DesiredAccess], rax; __int64
0x14001176e  call    NpCreateClientEnd
0x140011773  movups  xmm0, xmmword ptr [rax]
0x140011776  movups  xmmword ptr [rbx+30h], xmm0
0x14001177a  mov     edi, [rbx+30h]
0x14001177d  lea     rax, [r13+0C0h]
0x140011784  test    r15d, r15d
0x140011787  jnz     loc_140011A7E
0x14001178d  test    r12, r12
0x140011790  jz      short loc_1400117B4
0x140011792  mov     eax, 202h
0x140011797  cmp     [r12], ax
0x14001179c  jnz     short loc_1400117B4
0x14001179e  lea     rcx, [r12+80h]
0x1400117a6  xor     edx, edx
0x1400117a8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400117af  nop     dword ptr [rax+rax+00h]
0x1400117b4  mov     rsi, [rbp+57h+var_60]
0x1400117b8  lea     rax, [rbp+57h+var_60]
0x1400117bc  cmp     rsi, rax
0x1400117bf  jz      short loc_1400117E2
0x1400117c1  lea     rcx, [rsi-0A8h]; Irp
0x1400117c8  mov     dl, 2; PriorityBoost
0x1400117ca  mov     rsi, [rsi]
0x1400117cd  call    cs:__imp_IofCompleteRequest
0x1400117d4  nop     dword ptr [rax+rax+00h]
0x1400117d9  lea     rax, [rbp+57h+var_60]
0x1400117dd  cmp     rsi, rax
0x1400117e0  jnz     short loc_1400117C1
0x1400117e2  call    cs:__imp_KeLeaveCriticalRegion
0x1400117e9  nop     dword ptr [rax+rax+00h]
0x1400117ee  jmp     loc_140011527
0x1400117f3  xor     eax, eax
0x1400117f5  mov     edi, 0C0000033h
0x1400117fa  test    r12, r12
0x1400117fd  setz    al
0x140011800  add     edi, eax
0x140011802  mov     rax, [rbp+57h+arg_18]
0x140011806  jmp     loc_140011784
0x14001180b  mov     eax, 206h
0x140011810  cmp     ax, r12w
0x140011814  jnz     loc_140011942
0x14001181a  call    cs:__imp_KeEnterCriticalRegion
0x140011821  nop     dword ptr [rax+rax+00h]
0x140011826  lea     r15, [r13+0C0h]
0x14001182d  xor     edx, edx
0x14001182f  mov     rcx, r15
0x140011832  mov     [rbp+57h+arg_18], r15
0x140011836  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001183d  nop     dword ptr [rax+rax+00h]
0x140011842  lea     r9, [rbp+57h+AccessStatus]
0x140011846  mov     r8b, 1
0x140011849  lea     rdx, [rbp+57h+UnicodeString]
0x14001184d  mov     rcx, r13
0x140011850  call    NpFindPrefix
0x140011855  mov     r12, rax
0x140011858  mov     eax, 202h
0x14001185d  test    r12, r12
0x140011860  jnz     loc_1400119F1
0x140011866  xor     edx, edx
0x140011868  mov     rcx, r15
0x14001186b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140011872  nop     dword ptr [rax+rax+00h]
0x140011877  jmp     loc_1400116D8
0x14001187c  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x140011880  call    cs:__imp_RtlFreeUnicodeString
0x140011887  nop     dword ptr [rax+rax+00h]
0x14001188c  jmp     loc_140011545
0x140011891  mov     rax, r10
0x140011894  jmp     loc_140011624
0x140011899  test    r15, r15
0x14001189c  jnz     loc_140011931
0x1400118a2  mov     r15d, 1
0x1400118a8  mov     [rbp+57h+AccessState], r10
0x1400118ac  mov     [r14+20h], r15
0x1400118b0  mov     [r14+18h], r13
0x1400118b4  lock inc dword ptr [r13+78h]
0x1400118b9  mov     [rbp+57h+AccessState+8], r15
0x1400118bd  movups  xmm0, xmmword ptr [rbp+57h+AccessState]
0x1400118c1  movups  xmmword ptr [rbx+30h], xmm0
0x1400118c5  mov     edi, [rbx+30h]
0x1400118c8  jmp     loc_140011527
0x1400118cd  mov     eax, 206h
0x1400118d2  cmp     ax, r12w
0x1400118d6  jz      loc_14001158A
0x1400118dc  jmp     loc_140011604
0x1400118e1  test    r15, r15
0x1400118e4  jnz     loc_140011522
0x1400118ea  shr     ecx, 18h
0x1400118ed  cmp     ecx, 1
0x1400118f0  jz      loc_1400119BA
0x1400118f6  lea     eax, [rcx-2]
0x1400118f9  cmp     eax, 1
0x1400118fc  ja      loc_140011522
0x140011902  mov     dword ptr [rsp+0F0h+var_C0], ecx; int
0x140011906  lea     rcx, [rbp+57h+AccessStatus]; int
0x14001190a  mov     [rsp+0F0h+PreviousMode], r9b; PreviousMode
0x14001190f  mov     r9, rdx; int
0x140011912  mov     [rsp+0F0h+DesiredAccess], r8d; DesiredAccess
0x140011917  mov     rdx, r13; int
0x14001191a  mov     r8, r14; int
0x14001191d  call    NpCreateNamedPipePrefix
0x140011922  movups  xmm0, xmmword ptr [rax]
0x140011925  movups  xmmword ptr [rbx+30h], xmm0
0x140011929  mov     edi, [rbx+30h]
0x14001192c  jmp     loc_140011527
0x140011931  mov     eax, 201h
0x140011936  cmp     ax, r12w
0x14001193a  jz      loc_1400118A2
0x140011940  jmp     short loc_1400118CD
0x140011942  mov     eax, 202h
0x140011947  cmp     r12w, ax
0x14001194b  jnz     loc_140011522
0x140011951  cmp     [rbp+57h+UnicodeString.Length], 0
0x140011956  jnz     loc_140011522
0x14001195c  mov     rax, [r15+20h]
0x140011960  and     rax, 0FFFFFFFFFFFFFFFCh
  ... truncated ...
```
