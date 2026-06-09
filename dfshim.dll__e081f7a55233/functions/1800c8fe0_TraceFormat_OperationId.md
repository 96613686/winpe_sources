# TraceFormat_OperationId

- ea: `0x1800c8fe0`
- end: `0x1800c912f`
- name: `TraceFormat_OperationId`
- size: `335`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800c8fe0`
- `0x18012a020`

## string_xrefs

- `0x1800c9083`: `COMPONENT_STORE_OPERATION_INSTALL_COMPONENT`
- `0x1800c9077`: `COMPONENT_STORE_OPERATION_INSTALL_COMPONENT_FILE`
- `0x1800c906b`: `COMPONENT_STORE_OPERATION_UNINSTALL_COMPONENT`
- `0x1800c905f`: `COMPONENT_STORE_OPERATION_SET_DEPLOYMENT_METADATA`
- `0x1800c9053`: `COMPONENT_STORE_OPERATION_INSTALL_PRIVATE_COMPONENT`
- `0x1800c9047`: `COMPONENT_STORE_OPERATION_INSTALL_PRIVATE_COMPONENT_FILE`
- `0x1800c902f`: `COMPONENT_STORE_OPERATION_REMOVE_DEPLOYMENT_PIN`
- `0x1800c903b`: `COMPONENT_STORE_OPERATION_ADD_DEPLOYMENT_PIN`
- `0x1800c9023`: `COMPONENT_STORE_OPERATION_LOCK_COMPONENT`
- `0x1800c908f`: `COMPONENT_STORE_OPERATION_UNLOCK_COMPONENT`
- `0x1800c9119`: `COMPONENT_STORE_OPERATION_LOCK_COMPONENT_PATH`
- `0x1800c9110`: `COMPONENT_STORE_OPERATION_UNLOCK_COMPONENT_PATH`
- `0x1800c9107`: `COMPONENT_STORE_OPERATION_LOCK_APPLICATION`
- `0x1800c90fe`: `COMPONENT_STORE_OPERATION_UNLOCK_APPLICATION`
- `0x1800c90f5`: `COMPONENT_STORE_OPERATION_LOCK_APPLICATION_PATH`
- `0x1800c90ec`: `COMPONENT_STORE_OPERATION_UNLOCK_APPLICATION_PATH`
- `0x1800c90e3`: `COMPONENT_STORE_OPERATION_SCAVENGE`
- `0x1800c90da`: `COMPONENT_STORE_OPERATION_INSTALL_DEPLOYMENT`
- `0x1800c90d1`: `COMPONENT_STORE_OPERATION_UNINSTALL_DEPLOYMENT`

## pseudocode

```c
__int64 __fastcall TraceFormat_OperationId(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edx
  unsigned int v3; // edx
  unsigned int v4; // edx
  unsigned int v5; // edx
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned int v8; // edx
  const char *v9; // rdx
  unsigned int v10; // edx
  unsigned int v11; // edx
  unsigned int v12; // edx
  unsigned int v13; // edx
  unsigned int v14; // edx
  unsigned int v15; // edx
  unsigned int v16; // edx
  unsigned int v17; // edx

  if ( a2 > 0xA )
  {
    v10 = a2 - 11;
    if ( !v10 )
    {
      v9 = "COMPONENT_STORE_OPERATION_LOCK_COMPONENT_PATH";
      return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v9 = "COMPONENT_STORE_OPERATION_UNLOCK_COMPONENT_PATH";
      return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v9 = "COMPONENT_STORE_OPERATION_LOCK_APPLICATION";
      return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      v9 = "COMPONENT_STORE_OPERATION_UNLOCK_APPLICATION";
      return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      v9 = "COMPONENT_STORE_OPERATION_LOCK_APPLICATION_PATH";
      return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
      v9 = "COMPONENT_STORE_OPERATION_UNLOCK_APPLICATION_PATH";
      return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
    }
    v16 = v15 - 1;
    if ( !v16 )
    {
      v9 = "COMPONENT_STORE_OPERATION_SCAVENGE";
      return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
    }
    v17 = v16 - 1;
    if ( !v17 )
    {
      v9 = "COMPONENT_STORE_OPERATION_INSTALL_DEPLOYMENT";
      return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
    }
    if ( v17 == 1 )
    {
      v9 = "COMPONENT_STORE_OPERATION_UNINSTALL_DEPLOYMENT";
      return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
    }
    goto LABEL_31;
  }
  if ( a2 == 10 )
  {
    v9 = "COMPONENT_STORE_OPERATION_UNLOCK_COMPONENT";
    return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
  }
  if ( !a2 )
  {
    v9 = "COMPONENT_STORE_OPERATION_INSTALL_COMPONENT";
    return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
  }
  v2 = a2 - 1;
  if ( !v2 )
  {
    v9 = "COMPONENT_STORE_OPERATION_INSTALL_COMPONENT_FILE";
    return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
  }
  v3 = v2 - 1;
  if ( !v3 )
  {
    v9 = "COMPONENT_STORE_OPERATION_UNINSTALL_COMPONENT";
    return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v9 = "COMPONENT_STORE_OPERATION_SET_DEPLOYMENT_METADATA";
    return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v9 = "COMPONENT_STORE_OPERATION_INSTALL_PRIVATE_COMPONENT";
    return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v9 = "COMPONENT_STORE_OPERATION_INSTALL_PRIVATE_COMPONENT_FILE";
    return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
  }
  v7 = v6 - 2;
  if ( !v7 )
  {
    v9 = "COMPONENT_STORE_OPERATION_ADD_DEPLOYMENT_PIN";
    return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v9 = "COMPONENT_STORE_OPERATION_REMOVE_DEPLOYMENT_PIN";
    return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
  }
  if ( v8 != 1 )
  {
LABEL_31:
    v9 = "Invalid Operation Id";
    return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
  }
  v9 = "COMPONENT_STORE_OPERATION_LOCK_COMPONENT";
  return (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)a1 + 168LL))(a1, v9);
}

```

## disassembly

```asm
0x1800c8fe0  cmp     edx, 0Ah
0x1800c8fe3  ja      loc_1800C909B
0x1800c8fe9  jz      loc_1800C908F
0x1800c8fef  test    edx, edx
0x1800c8ff1  jz      loc_1800C9083
0x1800c8ff7  sub     edx, 1
0x1800c8ffa  jz      short loc_1800C9077
0x1800c8ffc  sub     edx, 1
0x1800c8fff  jz      short loc_1800C906B
0x1800c9001  sub     edx, 1
0x1800c9004  jz      short loc_1800C905F
0x1800c9006  sub     edx, 1
0x1800c9009  jz      short loc_1800C9053
0x1800c900b  sub     edx, 1
0x1800c900e  jz      short loc_1800C9047
0x1800c9010  sub     edx, 2
0x1800c9013  jz      short loc_1800C903B
0x1800c9015  sub     edx, 1
0x1800c9018  jz      short loc_1800C902F
0x1800c901a  cmp     edx, 1
0x1800c901d  jnz     loc_1800C90C8
0x1800c9023  lea     rdx, aComponentStore_18; "COMPONENT_STORE_OPERATION_LOCK_COMPONEN"...
0x1800c902a  jmp     loc_1800C9120
0x1800c902f  lea     rdx, aComponentStore_13; "COMPONENT_STORE_OPERATION_REMOVE_DEPLOY"...
0x1800c9036  jmp     loc_1800C9120
0x1800c903b  lea     rdx, aComponentStore_8; "COMPONENT_STORE_OPERATION_ADD_DEPLOYMEN"...
0x1800c9042  jmp     loc_1800C9120
0x1800c9047  lea     rdx, aComponentStore_17; "COMPONENT_STORE_OPERATION_INSTALL_PRIVA"...
0x1800c904e  jmp     loc_1800C9120
0x1800c9053  lea     rdx, aComponentStore_5; "COMPONENT_STORE_OPERATION_INSTALL_PRIVA"...
0x1800c905a  jmp     loc_1800C9120
0x1800c905f  lea     rdx, aComponentStore_16; "COMPONENT_STORE_OPERATION_SET_DEPLOYMEN"...
0x1800c9066  jmp     loc_1800C9120
0x1800c906b  lea     rdx, aComponentStore_2; "COMPONENT_STORE_OPERATION_UNINSTALL_COM"...
0x1800c9072  jmp     loc_1800C9120
0x1800c9077  lea     rdx, aComponentStore_7; "COMPONENT_STORE_OPERATION_INSTALL_COMPO"...
0x1800c907e  jmp     loc_1800C9120
0x1800c9083  lea     rdx, aComponentStore_14; "COMPONENT_STORE_OPERATION_INSTALL_COMPO"...
0x1800c908a  jmp     loc_1800C9120
0x1800c908f  lea     rdx, aComponentStore_1; "COMPONENT_STORE_OPERATION_UNLOCK_COMPON"...
0x1800c9096  jmp     loc_1800C9120
0x1800c909b  sub     edx, 0Bh
0x1800c909e  jz      short loc_1800C9119
0x1800c90a0  sub     edx, 1
0x1800c90a3  jz      short loc_1800C9110
0x1800c90a5  sub     edx, 1
0x1800c90a8  jz      short loc_1800C9107
0x1800c90aa  sub     edx, 1
0x1800c90ad  jz      short loc_1800C90FE
0x1800c90af  sub     edx, 1
0x1800c90b2  jz      short loc_1800C90F5
0x1800c90b4  sub     edx, 1
0x1800c90b7  jz      short loc_1800C90EC
0x1800c90b9  sub     edx, 1
0x1800c90bc  jz      short loc_1800C90E3
0x1800c90be  sub     edx, 1
0x1800c90c1  jz      short loc_1800C90DA
0x1800c90c3  cmp     edx, 1
0x1800c90c6  jz      short loc_1800C90D1
0x1800c90c8  lea     rdx, aInvalidOperati; "Invalid Operation Id"
0x1800c90cf  jmp     short loc_1800C9120
0x1800c90d1  lea     rdx, aComponentStore_3; "COMPONENT_STORE_OPERATION_UNINSTALL_DEP"...
0x1800c90d8  jmp     short loc_1800C9120
0x1800c90da  lea     rdx, aComponentStore_10; "COMPONENT_STORE_OPERATION_INSTALL_DEPLO"...
0x1800c90e1  jmp     short loc_1800C9120
0x1800c90e3  lea     rdx, aComponentStore_15; "COMPONENT_STORE_OPERATION_SCAVENGE"
0x1800c90ea  jmp     short loc_1800C9120
0x1800c90ec  lea     rdx, aComponentStore_11; "COMPONENT_STORE_OPERATION_UNLOCK_APPLIC"...
0x1800c90f3  jmp     short loc_1800C9120
0x1800c90f5  lea     rdx, aComponentStore_19; "COMPONENT_STORE_OPERATION_LOCK_APPLICAT"...
0x1800c90fc  jmp     short loc_1800C9120
0x1800c90fe  lea     rdx, aComponentStore_4; "COMPONENT_STORE_OPERATION_UNLOCK_APPLIC"...
0x1800c9105  jmp     short loc_1800C9120
0x1800c9107  lea     rdx, aComponentStore_6; "COMPONENT_STORE_OPERATION_LOCK_APPLICAT"...
0x1800c910e  jmp     short loc_1800C9120
0x1800c9110  lea     rdx, aComponentStore_9; "COMPONENT_STORE_OPERATION_UNLOCK_COMPON"...
0x1800c9117  jmp     short loc_1800C9120
0x1800c9119  lea     rdx, aComponentStore_0; "COMPONENT_STORE_OPERATION_LOCK_COMPONEN"...
0x1800c9120  mov     rax, [rcx]
0x1800c9123  mov     rax, [rax+0A8h]
0x1800c912a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
