# CLTPartitionUsers::UpdateStore(void)

- ea: `0x18004ebe0`
- end: `0x18004ef6c`
- name: `?UpdateStore@CLTPartitionUsers@@UEAAJXZ`
- size: `908`
- prototype: `__int64 __fastcall(CLTPartitionUsers *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18004e06c`
- `0x18004ebe0`
- `0x18004f074`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eefd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ef3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eefd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ef3f`

## pseudocode

```c
__int64 __fastcall CLTPartitionUsers::UpdateStore(CLTPartitionUsers *this)
{
  __int64 v2; // rcx
  int SidForName; // ebx
  int v4; // esi
  int v5; // eax
  __int64 v6; // rcx
  CLTPartitionUsers *v7; // rcx
  unsigned __int16 *v9; // [rsp+58h] [rbp-10h] BYREF
  unsigned int v10; // [rsp+90h] [rbp+28h] BYREF
  int v11; // [rsp+98h] [rbp+30h] BYREF
  __int64 v12; // [rsp+A0h] [rbp+38h]
  LPVOID pv; // [rsp+A8h] [rbp+40h] BYREF

  if ( !*((_QWORD *)this + 9) || (*((_DWORD *)this + 8) & 0x40000) != 0 )
    return 2147549183LL;
  v2 = *((_QWORD *)this + 10);
  v12 = 0;
  pv = 0;
  SidForName = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *))(*(_QWORD *)v2 + 24LL))(
                 v2,
                 &didCOMSERVICES,
                 &tidCOMSERVICES_PARTITION_USERS);
  if ( SidForName >= 0 )
  {
    SidForName = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 24LL))(v12);
    if ( SidForName >= 0 )
    {
      SidForName = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 104LL))(*((_QWORD *)this + 9));
      if ( SidForName >= 0 )
      {
        v4 = 0;
        v11 = 0;
        v10 = 0;
        while ( 1 )
        {
          v5 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 9) + 112LL))(*((_QWORD *)this + 9), &v11);
          if ( v5 )
            break;
          if ( v11 == 3 )
          {
            SidForName = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 9) + 152LL))(
                           *((_QWORD *)this + 9),
                           1,
                           0);
            if ( SidForName < 0 )
              goto LABEL_33;
            SidForName = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v12 + 56LL))(
                           v12,
                           &v10,
                           &pv);
            if ( SidForName < 0 )
              goto LABEL_33;
            SidForName = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 136LL))(v12);
            if ( SidForName < 0 )
              goto LABEL_33;
          }
          else if ( v11 )
          {
            v6 = *((_QWORD *)this + 9);
            if ( v11 == 1 )
            {
              v9 = 0;
              SidForName = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, unsigned __int16 **))(*(_QWORD *)v6 + 152LL))(
                             v6,
                             0,
                             0,
                             0,
                             0,
                             &v9);
              if ( SidForName < 0 )
                goto LABEL_33;
              SidForName = CLTPartitionUsers::GetSidForName(v7, v9, &v10, &pv);
              if ( SidForName < 0 )
                goto LABEL_33;
              SidForName = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 120LL))(v12);
              if ( SidForName < 0 )
                goto LABEL_34;
              SidForName = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, LPVOID))(*(_QWORD *)v12 + 160LL))(
                             v12,
                             0,
                             v10,
                             pv);
              if ( SidForName < 0 )
                goto LABEL_34;
              v4 = 1;
            }
            else
            {
              SidForName = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned int *, LPVOID *))(*(_QWORD *)v6 + 152LL))(
                             v6,
                             1,
                             0,
                             0,
                             &v10,
                             &pv);
              if ( SidForName < 0 )
                goto LABEL_33;
              SidForName = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v12 + 56LL))(
                             v12,
                             &v10,
                             &pv);
              if ( SidForName < 0 )
                goto LABEL_33;
              SidForName = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 128LL))(v12);
              if ( SidForName < 0 )
                goto LABEL_33;
            }
            SidForName = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 9) + 152LL))(
                           *((_QWORD *)this + 9),
                           2,
                           0);
            if ( SidForName < 0 )
              goto LABEL_33;
            SidForName = CLTPartitionUsers::ValidatePartition((CLTPartitionUsers *)((char *)this - 8), 0);
            if ( SidForName < 0 )
              goto LABEL_33;
            SidForName = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v12 + 160LL))(
                           v12,
                           3,
                           0,
                           0);
            if ( SidForName < 0 )
              goto LABEL_33;
            SidForName = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 144LL))(v12);
            if ( SidForName < 0 )
              goto LABEL_33;
            if ( v4 )
            {
              CoTaskMemFree(pv);
              v4 = 0;
              pv = 0;
            }
          }
        }
        SidForName = 0;
        if ( v5 != -2146367487 )
          SidForName = v5;
        if ( SidForName >= 0 )
          SidForName = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 96LL))(v12);
LABEL_33:
        if ( !v4 )
          goto LABEL_36;
LABEL_34:
        if ( pv )
          CoTaskMemFree(pv);
      }
    }
  }
LABEL_36:
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)SidForName;
}

```

## disassembly

```asm
0x18004ebe0  push    rbp
0x18004ebe2  push    rbx
0x18004ebe3  push    rsi
0x18004ebe4  push    rdi
0x18004ebe5  mov     rbp, rsp
0x18004ebe8  sub     rsp, 68h
0x18004ebec  cmp     qword ptr [rcx+48h], 0
0x18004ebf1  mov     rdi, rcx
0x18004ebf4  jz      loc_18004EF5E
0x18004ebfa  test    dword ptr [rcx+20h], 40000h
0x18004ec01  jnz     loc_18004EF5E
0x18004ec07  mov     rcx, [rcx+50h]
0x18004ec0b  lea     r8, [rbp+arg_10]
0x18004ec0f  mov     r9, [rdi+28h]
0x18004ec13  xor     edx, edx
0x18004ec15  mov     [rsp+68h+var_30], r8
0x18004ec1a  test    r9, r9
0x18004ec1d  mov     [rbp+arg_10], 0
0x18004ec25  lea     r8, tidCOMSERVICES_PARTITION_USERS
0x18004ec2c  setnz   dl
0x18004ec2f  mov     [rbp+pv], 0
0x18004ec37  mov     rax, [rcx]
0x18004ec3a  mov     [rsp+68h+var_38], 0
0x18004ec42  mov     dword ptr [rsp+68h+var_40], 1
0x18004ec4a  mov     [rsp+68h+var_48], rdx
0x18004ec4f  lea     rdx, didCOMSERVICES
0x18004ec56  mov     rax, [rax+18h]
0x18004ec5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec5f  mov     ebx, eax
0x18004ec61  test    eax, eax
0x18004ec63  js      loc_18004EF45
0x18004ec69  mov     rcx, [rbp+arg_10]
0x18004ec6d  mov     rax, [rcx]
0x18004ec70  mov     rax, [rax+18h]
0x18004ec74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec79  mov     ebx, eax
0x18004ec7b  test    eax, eax
0x18004ec7d  js      loc_18004EF45
0x18004ec83  mov     rcx, [rdi+48h]
0x18004ec87  mov     rax, [rcx]
0x18004ec8a  mov     rax, [rax+68h]
0x18004ec8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec93  mov     ebx, eax
0x18004ec95  test    eax, eax
0x18004ec97  js      loc_18004EF45
0x18004ec9d  xor     esi, esi
0x18004ec9f  mov     [rbp+arg_8], esi
0x18004eca2  mov     [rbp+arg_0], esi
0x18004eca5  mov     rcx, [rdi+48h]
0x18004eca9  lea     rdx, [rbp+arg_8]
0x18004ecad  mov     rax, [rcx]
0x18004ecb0  mov     rax, [rax+70h]
0x18004ecb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ecb9  test    eax, eax
0x18004ecbb  jnz     loc_18004EF12
0x18004ecc1  mov     eax, [rbp+arg_8]
0x18004ecc4  mov     [rbp+var_18], 0
0x18004eccc  cmp     eax, 3
0x18004eccf  jnz     short loc_18004ED4E
0x18004ecd1  mov     rcx, [rdi+48h]
0x18004ecd5  lea     rdx, [rbp+pv]
0x18004ecd9  mov     [rsp+68h+var_40], rdx
0x18004ecde  xor     r9d, r9d
0x18004ece1  lea     rdx, [rbp+arg_0]
0x18004ece5  xor     r8d, r8d
0x18004ece8  mov     [rsp+68h+var_48], rdx
0x18004eced  mov     rax, [rcx]
0x18004ecf0  lea     edx, [r9+1]
0x18004ecf4  mov     rax, [rax+98h]
0x18004ecfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed00  mov     ebx, eax
0x18004ed02  test    eax, eax
0x18004ed04  js      loc_18004EF32
0x18004ed0a  mov     rcx, [rbp+arg_10]
0x18004ed0e  lea     r8, [rbp+pv]
0x18004ed12  lea     rdx, [rbp+arg_0]
0x18004ed16  mov     rax, [rcx]
0x18004ed19  mov     rax, [rax+38h]
0x18004ed1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed22  mov     ebx, eax
0x18004ed24  test    eax, eax
0x18004ed26  js      loc_18004EF32
0x18004ed2c  mov     rcx, [rbp+arg_10]
0x18004ed30  mov     rax, [rcx]
0x18004ed33  mov     rax, [rax+88h]
0x18004ed3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed3f  mov     ebx, eax
0x18004ed41  test    eax, eax
0x18004ed43  jns     loc_18004ECA5
0x18004ed49  jmp     loc_18004EF32
0x18004ed4e  test    eax, eax
0x18004ed50  jz      loc_18004ECA5
0x18004ed56  mov     rcx, [rdi+48h]
0x18004ed5a  xor     r9d, r9d
0x18004ed5d  xor     r8d, r8d
0x18004ed60  cmp     eax, 1
0x18004ed63  jnz     loc_18004EDF9
0x18004ed69  lea     rdx, [rbp+var_10]
0x18004ed6d  mov     [rbp+var_10], r8
0x18004ed71  mov     rax, [rcx]
0x18004ed74  mov     [rsp+68h+var_40], rdx
0x18004ed79  xor     edx, edx
0x18004ed7b  mov     [rsp+68h+var_48], r8
0x18004ed80  mov     rax, [rax+98h]
0x18004ed87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed8c  mov     ebx, eax
0x18004ed8e  test    eax, eax
0x18004ed90  js      loc_18004EF32
0x18004ed96  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18004ed9a  lea     r9, [rbp+pv]; void **
0x18004ed9e  lea     r8, [rbp+arg_0]; unsigned int *
0x18004eda2  call    ?GetSidForName@CLTPartitionUsers@@AEAAJPEAGPEAKPEAPEAX@Z; CLTPartitionUsers::GetSidForName(ushort *,ulong *,void * *)
0x18004eda7  mov     ebx, eax
0x18004eda9  test    eax, eax
0x18004edab  js      loc_18004EF32
0x18004edb1  mov     rcx, [rbp+arg_10]
0x18004edb5  mov     rax, [rcx]
0x18004edb8  mov     rax, [rax+78h]
0x18004edbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004edc1  mov     ebx, eax
0x18004edc3  test    eax, eax
0x18004edc5  js      loc_18004EF36
0x18004edcb  mov     rcx, [rbp+arg_10]
0x18004edcf  xor     edx, edx
0x18004edd1  mov     r9, [rbp+pv]
0x18004edd5  mov     r8d, [rbp+arg_0]
0x18004edd9  mov     rax, [rcx]
0x18004eddc  mov     rax, [rax+0A0h]
0x18004ede3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ede8  mov     ebx, eax
0x18004edea  test    eax, eax
0x18004edec  js      loc_18004EF36
0x18004edf2  mov     esi, 1
0x18004edf7  jmp     short loc_18004EE68
0x18004edf9  mov     rax, [rcx]
0x18004edfc  lea     rdx, [rbp+pv]
0x18004ee00  mov     [rsp+68h+var_40], rdx
0x18004ee05  lea     rdx, [rbp+arg_0]
0x18004ee09  mov     [rsp+68h+var_48], rdx
0x18004ee0e  mov     edx, 1
0x18004ee13  mov     rax, [rax+98h]
0x18004ee1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee1f  mov     ebx, eax
0x18004ee21  test    eax, eax
0x18004ee23  js      loc_18004EF32
0x18004ee29  mov     rcx, [rbp+arg_10]
0x18004ee2d  lea     r8, [rbp+pv]
0x18004ee31  lea     rdx, [rbp+arg_0]
0x18004ee35  mov     rax, [rcx]
0x18004ee38  mov     rax, [rax+38h]
0x18004ee3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee41  mov     ebx, eax
0x18004ee43  test    eax, eax
0x18004ee45  js      loc_18004EF32
0x18004ee4b  mov     rcx, [rbp+arg_10]
0x18004ee4f  mov     rax, [rcx]
0x18004ee52  mov     rax, [rax+80h]
0x18004ee59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee5e  mov     ebx, eax
0x18004ee60  test    eax, eax
0x18004ee62  js      loc_18004EF32
0x18004ee68  mov     rcx, [rdi+48h]
0x18004ee6c  lea     rdx, [rbp+var_18]
0x18004ee70  mov     [rsp+68h+var_40], rdx
0x18004ee75  xor     r9d, r9d
0x18004ee78  xor     r8d, r8d
0x18004ee7b  mov     [rsp+68h+var_48], 0
0x18004ee84  mov     rax, [rcx]
0x18004ee87  lea     edx, [r9+2]
0x18004ee8b  mov     rax, [rax+98h]
0x18004ee92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee97  mov     ebx, eax
0x18004ee99  test    eax, eax
0x18004ee9b  js      loc_18004EF32
0x18004eea1  mov     rdx, [rbp+var_18]; struct _GUID *
0x18004eea5  lea     rcx, [rdi-8]; this
0x18004eea9  call    ?ValidatePartition@CLTPartitionUsers@@AEAAJPEAU_GUID@@@Z; CLTPartitionUsers::ValidatePartition(_GUID *)
0x18004eeae  mov     ebx, eax
0x18004eeb0  test    eax, eax
0x18004eeb2  js      short loc_18004EF32
0x18004eeb4  mov     rcx, [rbp+arg_10]
0x18004eeb8  xor     r8d, r8d
0x18004eebb  mov     r9, [rbp+var_18]
0x18004eebf  mov     rax, [rcx]
0x18004eec2  lea     edx, [r8+3]
0x18004eec6  mov     rax, [rax+0A0h]
0x18004eecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eed2  mov     ebx, eax
0x18004eed4  test    eax, eax
0x18004eed6  js      short loc_18004EF32
0x18004eed8  mov     rcx, [rbp+arg_10]
0x18004eedc  mov     rax, [rcx]
0x18004eedf  mov     rax, [rax+90h]
0x18004eee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eeeb  mov     ebx, eax
0x18004eeed  test    eax, eax
0x18004eeef  js      short loc_18004EF32
0x18004eef1  test    esi, esi
0x18004eef3  jz      loc_18004ECA5
0x18004eef9  mov     rcx, [rbp+pv]; pv
0x18004eefd  call    cs:__imp_CoTaskMemFree
0x18004ef03  xor     esi, esi
0x18004ef05  mov     [rbp+pv], 0
0x18004ef0d  jmp     loc_18004ECA5
0x18004ef12  xor     ebx, ebx
0x18004ef14  cmp     eax, 80110801h
0x18004ef19  cmovnz  ebx, eax
0x18004ef1c  test    ebx, ebx
0x18004ef1e  js      short loc_18004EF32
0x18004ef20  mov     rcx, [rbp+arg_10]
0x18004ef24  mov     rax, [rcx]
0x18004ef27  mov     rax, [rax+60h]
0x18004ef2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef30  mov     ebx, eax
0x18004ef32  test    esi, esi
0x18004ef34  jz      short loc_18004EF45
0x18004ef36  mov     rcx, [rbp+pv]; pv
0x18004ef3a  test    rcx, rcx
0x18004ef3d  jz      short loc_18004EF45
0x18004ef3f  call    cs:__imp_CoTaskMemFree
0x18004ef45  mov     rcx, [rbp+arg_10]
0x18004ef49  test    rcx, rcx
0x18004ef4c  jz      short loc_18004EF5A
0x18004ef4e  mov     rax, [rcx]
0x18004ef51  mov     rax, [rax+10h]
0x18004ef55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef5a  mov     eax, ebx
0x18004ef5c  jmp     short loc_18004EF63
0x18004ef5e  mov     eax, 8000FFFFh
0x18004ef63  add     rsp, 68h
0x18004ef67  pop     rdi
0x18004ef68  pop     rsi
0x18004ef69  pop     rbx
0x18004ef6a  pop     rbp
0x18004ef6b  retn
```
