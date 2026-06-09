# TdiCreate

- ea: `0x140007d40`
- end: `0x1400080fb`
- name: `TdiCreate`
- size: `955`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140005cfc`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x140004a68`
- `0x140004e58`
- `0x1400051b4`
- `0x140007d40`
- `0x140009cc8`
- `0x14000a060`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x140007f68`
- `ntoskrnl!IoGetRequestorProcess` at `0x140007f68`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140007fb9`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140007fb9`
- `ntoskrnl!IoGetRequestorProcessId` at `0x140007ff5`
- `ntoskrnl!IoGetRequestorProcessId` at `0x140007ff5`

## pseudocode

```c
__int64 __fastcall TdiCreate(__int64 a1, IRP *a2)
{
  _IRP *MasterIrp; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  _IRP *i; // rdx
  __int64 v7; // r15
  unsigned __int16 v8; // ax
  unsigned __int16 v9; // r8
  __int16 v10; // ax
  int v11; // r9d
  int v12; // eax
  int v13; // edx
  int v14; // edx
  __int64 v15; // rax
  int v16; // r9d
  unsigned __int16 v17; // ax
  PEPROCESS RequestorProcess; // rax
  int v19; // edx
  PEPROCESS v20; // r14
  __int64 v21; // rax
  __int64 ProcessImageFileName; // rax
  int v23; // edx
  ULONG RequestorProcessId; // eax
  char v25; // cl
  void *v27; // [rsp+90h] [rbp+8h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      15,
      34,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      (char)a2);
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( MasterIrp )
  {
    v7 = *(_QWORD *)(a1 + 64);
    for ( i = a2->AssociatedIrp.MasterIrp; ; i = (_IRP *)((char *)i + v15) )
    {
      v8 = *((unsigned __int8 *)&i->Size + 3);
      if ( (_BYTE)v8 == 16 )
      {
        v9 = 0;
        while ( *((_BYTE *)&i->MdlAddress + v9) == aTransportaddre[v9] )
        {
          if ( ++v9 >= v8 )
          {
            if ( !i )
              goto LABEL_21;
            v10 = *(&i->Size + 2);
            v11 = (_DWORD)i + *((unsigned __int8 *)&i->Size + 3) + 9;
            v27 = 0;
            v12 = TdiOpenAddress(v7, CurrentStackLocation->FileObject, (unsigned int)&v27, v11, v10);
            LODWORD(MasterIrp) = v12;
            if ( v12 < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                return (unsigned int)MasterIrp;
              v16 = 37;
LABEL_20:
              WPP_RECORDER_SF_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v13,
                1,
                v16,
                (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
                v12);
            }
            else
            {
              v14 = (int)v27;
              CurrentStackLocation->FileObject->FsContext = v27;
              CurrentStackLocation->FileObject->FsContext2 = (void *)1;
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                return (unsigned int)MasterIrp;
              WPP_RECORDER_SF_qq(
                WPP_GLOBAL_Control->DeviceExtension,
                v14,
                15,
                36,
                (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
                v14,
                (char)CurrentStackLocation->FileObject);
            }
            goto LABEL_41;
          }
        }
      }
      v15 = *(unsigned int *)&i->Type;
      if ( !(_DWORD)v15 )
        break;
    }
    while ( 1 )
    {
LABEL_21:
      v17 = *((unsigned __int8 *)&MasterIrp->Size + 3);
      if ( (_BYTE)v17 == 17 )
      {
        LODWORD(i) = 0;
        while ( *((_BYTE *)&MasterIrp->MdlAddress + (unsigned __int16)i) == aConnectioncont[(unsigned __int16)i] )
        {
          LOWORD(i) = (_WORD)i + 1;
          if ( (unsigned __int16)i >= v17 )
          {
            if ( !MasterIrp )
              goto LABEL_38;
            v27 = 0;
            RequestorProcess = IoGetRequestorProcess(a2);
            v20 = RequestorProcess;
            if ( RequestorProcess )
            {
              ProcessImageFileName = PsGetProcessImageFileName(RequestorProcess);
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_s(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v23,
                  15,
                  39,
                  (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
                  ProcessImageFileName);
            }
            else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                v19,
                2,
                38,
                (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
            }
            RequestorProcessId = IoGetRequestorProcessId(a2);
            v12 = TdiOpenConnection(
                    v7,
                    CurrentStackLocation->FileObject,
                    v20,
                    RequestorProcessId,
                    &v27,
                    *(_MDL **)((char *)&MasterIrp->MdlAddress + *((unsigned __int8 *)&MasterIrp->Size + 3) + 1),
                    *(&MasterIrp->Size + 2));
            LODWORD(MasterIrp) = v12;
            if ( v12 >= 0 )
            {
              v25 = (char)v27;
              CurrentStackLocation->FileObject->FsContext = v27;
              CurrentStackLocation->FileObject->FsContext2 = (void *)2;
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                return (unsigned int)MasterIrp;
              WPP_RECORDER_SF_qq(
                WPP_GLOBAL_Control->DeviceExtension,
                v13,
                15,
                40,
                (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
                v25,
                (char)CurrentStackLocation->FileObject);
              goto LABEL_41;
            }
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return (unsigned int)MasterIrp;
            v16 = 41;
            goto LABEL_20;
          }
        }
      }
      v21 = *(unsigned int *)&MasterIrp->Type;
      if ( !(_DWORD)v21 )
        break;
      MasterIrp = (_IRP *)((char *)MasterIrp + v21);
    }
LABEL_38:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)i,
        1,
        42,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
    LODWORD(MasterIrp) = -2147483629;
  }
  else
  {
    CurrentStackLocation->FileObject->FsContext = (void *)1;
    CurrentStackLocation->FileObject->FsContext2 = (void *)3;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)MasterIrp;
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      15,
      35,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      (char)CurrentStackLocation->FileObject);
  }
LABEL_41:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)i,
      15,
      43,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  return (unsigned int)MasterIrp;
}

```

## disassembly

```asm
0x140007d40  push    rbx
0x140007d42  push    rbp
0x140007d43  push    rsi
0x140007d44  push    rdi
0x140007d45  push    r12
0x140007d47  push    r13
0x140007d49  push    r14
0x140007d4b  push    r15
0x140007d4d  sub     rsp, 48h
0x140007d51  mov     rbp, rdx
0x140007d54  mov     rsi, rcx
0x140007d57  lea     r12, WPP_RECORDER_INITIALIZED
0x140007d5e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140007d65  lea     r13, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140007d6c  jz      short loc_140007D92
0x140007d6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d75  mov     r9d, 22h ; '"'
0x140007d7b  mov     [rsp+88h+var_60], rdx
0x140007d80  mov     [rsp+88h+var_68], r13
0x140007d85  mov     rcx, [rcx+40h]
0x140007d89  lea     r8d, [r9-13h]
0x140007d8d  call    WPP_RECORDER_SF_q
0x140007d92  mov     rdi, [rbp+18h]
0x140007d96  mov     rbx, [rbp+0B8h]
0x140007d9d  test    rdi, rdi
0x140007da0  jnz     short loc_140007DF3
0x140007da2  mov     rax, [rbx+30h]
0x140007da6  mov     esi, 1
0x140007dab  mov     [rax+18h], rsi
0x140007daf  mov     rax, [rbx+30h]
0x140007db3  mov     qword ptr [rax+20h], 3
0x140007dbb  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140007dc2  jz      loc_1400080E7
0x140007dc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140007dcf  lea     r9d, [rsi+22h]
0x140007dd3  mov     rax, [rbx+30h]
0x140007dd7  lea     r8d, [rsi+0Eh]
0x140007ddb  mov     [rsp+88h+var_60], rax
0x140007de0  mov     [rsp+88h+var_68], r13
0x140007de5  mov     rcx, [rcx+40h]
0x140007de9  call    WPP_RECORDER_SF_q
0x140007dee  jmp     loc_1400080BF
0x140007df3  mov     r15, [rsi+40h]
0x140007df7  lea     r10, cs:140000000h
0x140007dfe  mov     esi, 1
0x140007e03  mov     rdx, rdi
0x140007e06  movzx   eax, byte ptr [rdx+5]
0x140007e0a  cmp     al, 10h
0x140007e0c  jnz     loc_140007EDE
0x140007e12  movzx   r9d, ax
0x140007e16  xor     r8d, r8d
0x140007e19  xor     eax, eax
0x140007e1b  cmp     ax, r9w
0x140007e1f  jnb     short loc_140007E41
0x140007e21  movzx   ecx, r8w
0x140007e25  mov     al, [rcx+r10+22A80h]
0x140007e2d  cmp     [rcx+rdx+8], al
0x140007e31  jnz     loc_140007EDE
0x140007e37  add     r8w, si
0x140007e3b  cmp     r8w, r9w
0x140007e3f  jb      short loc_140007E21
0x140007e41  test    rdx, rdx
0x140007e44  jz      loc_140007F20
0x140007e4a  movzx   r9d, byte ptr [rdx+5]
0x140007e4f  lea     r8, [rsp+88h+arg_0]
0x140007e57  movzx   eax, word ptr [rdx+6]
0x140007e5b  add     r9, 9
0x140007e5f  add     r9, rdx
0x140007e62  mov     [rsp+88h+arg_0], 0
0x140007e6e  mov     rdx, [rbx+30h]
0x140007e72  mov     rcx, r15
0x140007e75  mov     word ptr [rsp+88h+var_68], ax
0x140007e7a  call    TdiOpenAddress
0x140007e7f  mov     edi, eax
0x140007e81  test    eax, eax
0x140007e83  js      short loc_140007EEC
0x140007e85  mov     rcx, [rbx+30h]
0x140007e89  mov     rdx, [rsp+88h+arg_0]
0x140007e91  mov     [rcx+18h], rdx
0x140007e95  mov     rcx, [rbx+30h]
0x140007e99  mov     [rcx+20h], rsi
0x140007e9d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140007ea4  jz      loc_1400080E7
0x140007eaa  mov     rax, [rbx+30h]
0x140007eae  mov     r9d, 24h ; '$'
0x140007eb4  mov     [rsp+88h+var_58], rax
0x140007eb9  mov     [rsp+88h+var_60], rdx
0x140007ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ec5  mov     r8d, 0Fh
0x140007ecb  mov     [rsp+88h+var_68], r13
0x140007ed0  mov     rcx, [rcx+40h]
0x140007ed4  call    WPP_RECORDER_SF_qq
0x140007ed9  jmp     loc_1400080BF
0x140007ede  mov     eax, [rdx]
0x140007ee0  test    eax, eax
0x140007ee2  jz      short loc_140007F20
0x140007ee4  add     rdx, rax
0x140007ee7  jmp     loc_140007E06
0x140007eec  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140007ef3  jz      loc_1400080E7
0x140007ef9  mov     r9d, 25h ; '%'
0x140007eff  mov     rcx, cs:WPP_GLOBAL_Control
0x140007f06  mov     r8d, esi
0x140007f09  mov     dword ptr [rsp+88h+var_60], eax
0x140007f0d  mov     [rsp+88h+var_68], r13
0x140007f12  mov     rcx, [rcx+40h]
0x140007f16  call    WPP_RECORDER_SF_d
0x140007f1b  jmp     loc_1400080BF
0x140007f20  movzx   eax, byte ptr [rdi+5]
0x140007f24  cmp     al, 11h
0x140007f26  jnz     short loc_140007FA4
0x140007f28  movzx   r8d, ax
0x140007f2c  xor     edx, edx
0x140007f2e  xor     eax, eax
0x140007f30  cmp     ax, r8w
0x140007f34  jnb     short loc_140007F50
0x140007f36  movzx   ecx, dx
0x140007f39  mov     al, [rcx+r10+22A98h]
0x140007f41  cmp     [rcx+rdi+8], al
0x140007f45  jnz     short loc_140007FA4
0x140007f47  add     dx, si
0x140007f4a  cmp     dx, r8w
0x140007f4e  jb      short loc_140007F36
0x140007f50  test    rdi, rdi
0x140007f53  jz      loc_140008093
0x140007f59  mov     rcx, rbp; Irp
0x140007f5c  mov     [rsp+88h+arg_0], 0
0x140007f68  call    cs:__imp_IoGetRequestorProcess
0x140007f6f  nop     dword ptr [rax+rax+00h]
0x140007f74  mov     r14, rax
0x140007f77  test    rax, rax
0x140007f7a  jnz     short loc_140007FB6
0x140007f7c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140007f83  jz      short loc_140007FF2
0x140007f85  mov     rcx, cs:WPP_GLOBAL_Control
0x140007f8c  lea     r9d, [rax+26h]
0x140007f90  lea     r8d, [rax+2]
0x140007f94  mov     [rsp+88h+var_68], r13
0x140007f99  mov     rcx, [rcx+40h]
0x140007f9d  call    WPP_RECORDER_SF_
0x140007fa2  jmp     short loc_140007FF2
0x140007fa4  mov     eax, [rdi]
0x140007fa6  test    eax, eax
0x140007fa8  jz      loc_140008093
0x140007fae  add     rdi, rax
0x140007fb1  jmp     loc_140007F20
0x140007fb6  mov     rcx, r14
0x140007fb9  call    cs:__imp_PsGetProcessImageFileName
0x140007fc0  nop     dword ptr [rax+rax+00h]
0x140007fc5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140007fcc  jz      short loc_140007FF2
0x140007fce  mov     rcx, cs:WPP_GLOBAL_Control
0x140007fd5  mov     r9d, 27h ; '''
0x140007fdb  mov     [rsp+88h+var_60], rax
0x140007fe0  mov     [rsp+88h+var_68], r13
0x140007fe5  mov     rcx, [rcx+40h]
0x140007fe9  lea     r8d, [r9-18h]
0x140007fed  call    WPP_RECORDER_SF_s
0x140007ff2  mov     rcx, rbp; Irp
0x140007ff5  call    cs:__imp_IoGetRequestorProcessId
0x140007ffc  nop     dword ptr [rax+rax+00h]
0x140008001  movzx   edx, byte ptr [rdi+5]
0x140008005  mov     r8, r14
0x140008008  movzx   ecx, word ptr [rdi+6]
0x14000800c  mov     r9d, eax
0x14000800f  mov     word ptr [rsp+88h+var_58], cx
0x140008014  mov     rcx, [rdx+rdi+9]
0x140008019  mov     rdx, [rbx+30h]
0x14000801d  mov     [rsp+88h+var_60], rcx
0x140008022  lea     rcx, [rsp+88h+arg_0]
0x14000802a  mov     [rsp+88h+var_68], rcx
0x14000802f  mov     rcx, r15
0x140008032  call    TdiOpenConnection
0x140008037  mov     edi, eax
0x140008039  test    eax, eax
0x14000803b  js      short loc_14000807F
0x14000803d  mov     rax, [rbx+30h]
0x140008041  mov     rcx, [rsp+88h+arg_0]
0x140008049  mov     [rax+18h], rcx
0x14000804d  mov     rax, [rbx+30h]
0x140008051  mov     qword ptr [rax+20h], 2
0x140008059  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140008060  jz      loc_1400080E7
0x140008066  mov     rax, [rbx+30h]
0x14000806a  mov     r9d, 28h ; '('
0x140008070  mov     [rsp+88h+var_58], rax
0x140008075  mov     [rsp+88h+var_60], rcx
0x14000807a  jmp     loc_140007EBE
0x14000807f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140008086  jz      short loc_1400080E7
0x140008088  mov     r9d, 29h ; ')'
0x14000808e  jmp     loc_140007EFF
0x140008093  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000809a  jz      short loc_1400080BA
0x14000809c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400080a3  mov     r9d, 2Ah ; '*'
0x1400080a9  mov     r8d, esi
0x1400080ac  mov     [rsp+88h+var_68], r13
0x1400080b1  mov     rcx, [rcx+40h]
0x1400080b5  call    WPP_RECORDER_SF_
0x1400080ba  mov     edi, 80000013h
0x1400080bf  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400080c6  jz      short loc_1400080E7
0x1400080c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400080cf  mov     r9d, 2Bh ; '+'
0x1400080d5  mov     [rsp+88h+var_68], r13
0x1400080da  mov     rcx, [rcx+40h]
0x1400080de  lea     r8d, [r9-1Ch]
0x1400080e2  call    WPP_RECORDER_SF_
0x1400080e7  mov     eax, edi
0x1400080e9  add     rsp, 48h
0x1400080ed  pop     r15
0x1400080ef  pop     r14
0x1400080f1  pop     r13
0x1400080f3  pop     r12
0x1400080f5  pop     rdi
0x1400080f6  pop     rsi
0x1400080f7  pop     rbp
0x1400080f8  pop     rbx
0x1400080f9  retn
```
