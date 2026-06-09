# NbtDispatchCreate

- ea: `0x14004b7a0`
- end: `0x14004baba`
- name: `NbtDispatchCreate`
- size: `794`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006900`
- `0x14000dc40`
- `0x1400148a0`
- `0x140027ebc`
- `0x1400400a4`
- `0x140040164`
- `0x140040214`
- `0x14004025c`
- `0x140040428`
- `0x14004b7a0`
- `0x14004bac0`
- `0x14004bb10`
- `0x14004bd7c`
- `0x14004bf14`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14004b8ae`
- `ntoskrnl!IofCompleteRequest` at `0x14004b8ae`

## pseudocode

```c
__int64 __fastcall NbtDispatchCreate(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  struct _IO_STACK_LOCATION *v8; // rax
  unsigned __int8 Control; // r15
  struct _IRP *MasterIrp; // rdi
  struct _IO_STACK_LOCATION *v11; // rcx
  int v12; // esi
  __int64 v14; // rax
  __int64 v15; // r9
  struct _IO_STACK_LOCATION *v16; // rdi
  PFILE_OBJECT FileObject; // rax
  _QWORD *v18; // r9
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rcx
  _QWORD *v22; // [rsp+30h] [rbp-38h] BYREF
  __int128 v23; // [rsp+38h] [rbp-30h]
  __int64 v24; // [rsp+48h] [rbp-20h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( (unsigned __int8)NBT_REFERENCE_DEVICE(a1, 0, 0) )
  {
    v8 = a2->Tail.Overlay.CurrentStackLocation;
    Control = CurrentStackLocation->Control;
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = 259;
    v8->Control |= 1u;
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    if ( (xmmword_140038420 & 4) != 0 )
      WPP_SF_DDq(
        v6,
        v5,
        v7,
        CurrentStackLocation->MajorFunction,
        CurrentStackLocation->MinorFunction,
        a2->AssociatedIrp.MasterIrp);
    if ( MasterIrp )
    {
      v14 = FindInEA(MasterIrp, "ConnectionContext");
      if ( v14 )
      {
        v15 = *(unsigned __int16 *)(v14 + 6);
        v24 = 0;
        v22 = 0;
        v23 = 0;
        if ( (unsigned int)v15 < 8 )
        {
          if ( (xmmword_140038420 & 0x40) != 0 )
            WPP_SF_dq(1030, 15, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, v15, 8);
          v12 = -1073741305;
        }
        else
        {
          v16 = a2->Tail.Overlay.CurrentStackLocation;
          v12 = NbtOpenConnection(&v22, *(_QWORD *)(*(unsigned __int8 *)(v14 + 5) + v14 + 9), a1);
          FileObject = v16->FileObject;
          if ( v12 < 0 )
          {
            FileObject->FsContext = 0;
            if ( (BYTE2(xmmword_140038420) & 8) != 0 )
              WPP_SF_d(1043, 16, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, (unsigned int)v12);
          }
          else
          {
            v18 = v22;
            if ( v22 )
            {
              FileObject->FsContext = v22;
              if ( *((_DWORD *)v18 + 4) == 829321027 )
              {
                FileObject->FsContext2 = (PVOID)2;
                v18[11] = FileObject;
                if ( (BYTE2(xmmword_140038420) & 8) != 0 )
                  WPP_SF_q(1043, 17, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, v18);
                goto LABEL_6;
              }
              v12 = -1073741823;
            }
          }
        }
      }
      else
      {
        v19 = FindInEA(MasterIrp, "TransportAddress");
        if ( v19 )
        {
          v20 = NTOpenAddr(a1, a2, v19);
        }
        else
        {
          if ( !FindInEA(MasterIrp, "WinsInterface") || *(&MasterIrp->Size + 2) < 4u )
          {
            v12 = -2147483629;
            goto LABEL_8;
          }
          if ( !*(_DWORD *)((char *)&MasterIrp->MdlAddress + *((unsigned __int8 *)&MasterIrp->Size + 3) + 1) )
          {
            v12 = -1073741503;
            goto LABEL_8;
          }
          v20 = NTOpenWinsAddr(v21, a2);
        }
        v12 = v20;
      }
    }
    else
    {
      v11 = a2->Tail.Overlay.CurrentStackLocation;
      v11->FileObject->FsContext2 = (PVOID)3;
      v11->FileObject->FsContext = (PVOID)qword_1400394B8;
      if ( *(_QWORD *)(a1 + 664) )
      {
LABEL_6:
        v12 = 0;
        goto LABEL_7;
      }
      v12 = NbtTdiOpenControl(a1);
    }
LABEL_7:
    if ( v12 == 259 )
    {
LABEL_9:
      NBT_DEREFERENCE_DEVICE(a1, 0);
      return (unsigned int)v12;
    }
LABEL_8:
    CurrentStackLocation->Control = Control;
    ReturnIrp(a2);
    goto LABEL_9;
  }
  if ( (xmmword_140038420 & 4) != 0 )
    WPP_SF_qD(
      1026,
      20,
      WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids,
      a1,
      CurrentStackLocation->Parameters.Read.ByteOffset.LowPart);
  a2->IoStatus.Status = -1073741436;
  IofCompleteRequest(a2, 2);
  return 3221225860LL;
}

```

## disassembly

```asm
0x14004b7a0  push    rbx
0x14004b7a2  push    rbp
0x14004b7a3  push    r14
0x14004b7a5  sub     rsp, 50h
0x14004b7a9  mov     r14, [rdx+0B8h]
0x14004b7b0  mov     rbx, rdx
0x14004b7b3  xor     edx, edx
0x14004b7b5  xor     r8d, r8d
0x14004b7b8  mov     rbp, rcx
0x14004b7bb  call    NBT_REFERENCE_DEVICE
0x14004b7c0  test    al, al
0x14004b7c2  jz      loc_14004B895
0x14004b7c8  mov     rax, [rbx+0B8h]
0x14004b7cf  mov     [rsp+68h+arg_0], rsi
0x14004b7d4  mov     [rsp+68h+arg_8], rdi
0x14004b7d9  mov     [rsp+68h+arg_10], r12
0x14004b7e1  xor     r12d, r12d
0x14004b7e4  mov     [rsp+68h+arg_18], r15
0x14004b7ec  movzx   r15d, byte ptr [r14+3]
0x14004b7f1  mov     [rbx+38h], r12
0x14004b7f5  mov     dword ptr [rbx+30h], 103h
0x14004b7fc  or      byte ptr [rax+3], 1
0x14004b800  mov     rdi, [rbx+18h]
0x14004b804  test    byte ptr cs:xmmword_140038420, 4
0x14004b80b  jnz     loc_14004B9DB
0x14004b811  test    rdi, rdi
0x14004b814  jnz     loc_14004B8C9
0x14004b81a  mov     rcx, [rbx+0B8h]
0x14004b821  mov     rax, [rcx+30h]
0x14004b825  mov     qword ptr [rax+20h], 3
0x14004b82d  mov     rcx, [rcx+30h]
0x14004b831  mov     rax, cs:qword_1400394B8
0x14004b838  mov     [rcx+18h], rax
0x14004b83c  cmp     [rbp+298h], r12
0x14004b843  jz      loc_14004B9CC
0x14004b849  mov     esi, r12d
0x14004b84c  cmp     esi, 103h
0x14004b852  jz      short loc_14004B862
0x14004b854  mov     edx, esi
0x14004b856  mov     [r14+3], r15b
0x14004b85a  mov     rcx, rbx; Irp
0x14004b85d  call    ReturnIrp
0x14004b862  xor     r8d, r8d
0x14004b865  xor     edx, edx
0x14004b867  mov     rcx, rbp
0x14004b86a  call    NBT_DEREFERENCE_DEVICE
0x14004b86f  mov     r15, [rsp+68h+arg_18]
0x14004b877  mov     eax, esi
0x14004b879  mov     rsi, [rsp+68h+arg_0]
0x14004b87e  mov     r12, [rsp+68h+arg_10]
0x14004b886  mov     rdi, [rsp+68h+arg_8]
0x14004b88b  add     rsp, 50h
0x14004b88f  pop     r14
0x14004b891  pop     rbp
0x14004b892  pop     rbx
0x14004b893  retn
0x14004b895  test    byte ptr cs:xmmword_140038420, 4
0x14004b89c  jnz     loc_14004B9F7
0x14004b8a2  mov     dl, 2; PriorityBoost
0x14004b8a4  mov     dword ptr [rbx+30h], 0C0000184h
0x14004b8ab  mov     rcx, rbx; Irp
0x14004b8ae  call    cs:__imp_IofCompleteRequest
0x14004b8b5  nop     dword ptr [rax+rax+00h]
0x14004b8ba  mov     eax, 0C0000184h
0x14004b8bf  add     rsp, 50h
0x14004b8c3  pop     r14
0x14004b8c5  pop     rbp
0x14004b8c6  pop     rbx
0x14004b8c7  retn
0x14004b8c9  lea     rdx, aConnectioncont; "ConnectionContext"
0x14004b8d0  mov     rcx, rdi
0x14004b8d3  call    FindInEA
0x14004b8d8  test    rax, rax
0x14004b8db  jz      loc_14004B97E
0x14004b8e1  movzx   r9d, word ptr [rax+6]
0x14004b8e6  xorps   xmm0, xmm0
0x14004b8e9  mov     [rsp+68h+var_20], r12
0x14004b8ee  mov     [rsp+68h+var_38], r12
0x14004b8f3  movdqu  [rsp+68h+var_30], xmm0
0x14004b8f9  cmp     r9d, 8
0x14004b8fd  jb      loc_14004B9AB
0x14004b903  movzx   edx, byte ptr [rax+5]
0x14004b907  lea     rcx, [rsp+68h+var_38]
0x14004b90c  mov     rdi, [rbx+0B8h]
0x14004b913  mov     r8, rbp
0x14004b916  mov     rdx, [rdx+rax+9]
0x14004b91b  call    NbtOpenConnection
0x14004b920  mov     esi, eax
0x14004b922  mov     rax, [rdi+30h]
0x14004b926  test    esi, esi
0x14004b928  js      loc_14004BA77
0x14004b92e  mov     r9, [rsp+68h+var_38]
0x14004b933  test    r9, r9
0x14004b936  jz      loc_14004B84C
0x14004b93c  mov     [rax+18h], r9
0x14004b940  cmp     dword ptr [r9+10h], 316E6F43h
0x14004b948  jnz     short loc_14004B9C2
0x14004b94a  mov     qword ptr [rax+20h], 2
0x14004b952  mov     [r9+58h], rax
0x14004b956  test    byte ptr cs:xmmword_140038420+2, 8
0x14004b95d  jz      loc_14004B849
0x14004b963  mov     edx, 11h
0x14004b968  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x14004b96f  mov     ecx, 413h
0x14004b974  call    WPP_SF_q
0x14004b979  jmp     loc_14004B849
0x14004b97e  lea     rdx, aTransportaddre; "TransportAddress"
0x14004b985  mov     rcx, rdi
0x14004b988  call    FindInEA
0x14004b98d  test    rax, rax
0x14004b990  jz      loc_14004BA1D
0x14004b996  mov     r8, rax
0x14004b999  mov     rdx, rbx
0x14004b99c  mov     rcx, rbp
0x14004b99f  call    NTOpenAddr
0x14004b9a4  mov     esi, eax
0x14004b9a6  jmp     loc_14004B84C
0x14004b9ab  test    byte ptr cs:xmmword_140038420, 40h
0x14004b9b2  jnz     loc_14004BA53
0x14004b9b8  mov     esi, 0C0000207h
0x14004b9bd  jmp     loc_14004B84C
0x14004b9c2  mov     esi, 0C0000001h
0x14004b9c7  jmp     loc_14004B84C
0x14004b9cc  mov     rcx, rbp
0x14004b9cf  call    NbtTdiOpenControl
0x14004b9d4  mov     esi, eax
0x14004b9d6  jmp     loc_14004B84C
0x14004b9db  movzx   eax, byte ptr [r14+1]
0x14004b9e0  movzx   r9d, byte ptr [r14]
0x14004b9e4  mov     [rsp+68h+var_40], rdi
0x14004b9e9  mov     dword ptr [rsp+68h+var_48], eax
0x14004b9ed  call    WPP_SF_DDq
0x14004b9f2  jmp     loc_14004B811
0x14004b9f7  mov     eax, [r14+18h]
0x14004b9fb  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x14004ba02  mov     edx, 14h
0x14004ba07  mov     dword ptr [rsp+68h+var_48], eax
0x14004ba0b  mov     ecx, 402h
0x14004ba10  mov     r9, rbp
0x14004ba13  call    WPP_SF_qD
0x14004ba18  jmp     loc_14004B8A2
0x14004ba1d  lea     rdx, aWinsinterface; "WinsInterface"
0x14004ba24  mov     rcx, rdi
0x14004ba27  call    FindInEA
0x14004ba2c  test    rax, rax
0x14004ba2f  jz      short loc_14004BAB0
0x14004ba31  cmp     word ptr [rdi+6], 4
0x14004ba36  jb      short loc_14004BAB0
0x14004ba38  movzx   eax, byte ptr [rdi+5]
0x14004ba3c  mov     r8d, [rax+rdi+9]
0x14004ba41  test    r8d, r8d
0x14004ba44  jz      short loc_14004BAA6
0x14004ba46  mov     rdx, rbx
0x14004ba49  call    NTOpenWinsAddr
0x14004ba4e  jmp     loc_14004B9A4
0x14004ba53  mov     edx, 0Fh
0x14004ba58  mov     [rsp+68h+var_48], 8
0x14004ba61  mov     ecx, 406h
0x14004ba66  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x14004ba6d  call    WPP_SF_dq
0x14004ba72  jmp     loc_14004B9B8
0x14004ba77  mov     [rax+18h], r12
0x14004ba7b  test    byte ptr cs:xmmword_140038420+2, 8
0x14004ba82  jz      loc_14004B84C
0x14004ba88  mov     edx, 10h
0x14004ba8d  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x14004ba94  mov     ecx, 413h
0x14004ba99  mov     r9d, esi
0x14004ba9c  call    WPP_SF_d
0x14004baa1  jmp     loc_14004B84C
0x14004baa6  mov     esi, 0C0000141h
0x14004baab  jmp     loc_14004B854
0x14004bab0  mov     esi, 80000013h
0x14004bab5  jmp     loc_14004B854
```
