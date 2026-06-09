# Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(void *,_BLUETOOTH_SERVICE_RECORD *)

- ea: `0x180024c84`
- end: `0x180024eb3`
- name: `?BluetoothFindNextService@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_BLUETOOTH_SERVICE_RECORD@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *this, _QWORD *, struct _BLUETOOTH_SERVICE_RECORD *)`
- caller_count: `5`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025648`
- `0x180026650`
- `0x180026808`
- `0x180026dec`
- `0x180027ea8`

## callees

- `0x18000270c`
- `0x180024c84`
- `0x180026c70`
- `0x180027788`
- `0x180027848`
- `0x18002840c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024da4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024e8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024da4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024e8f`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(
        Microsoft::Bluetooth::Services::BthServ *this,
        _QWORD *a2,
        struct _BLUETOOTH_SERVICE_RECORD *a3)
{
  unsigned int v3; // ebx
  DWORD v6; // ecx
  Microsoft::Bluetooth::Services::BthServ *v7; // r15
  unsigned __int64 v8; // rdx
  unsigned __int32 v9; // ecx
  unsigned __int64 v10; // rax
  unsigned __int32 v11; // ecx
  unsigned __int16 v12; // ax
  int v13; // ecx
  __int64 v14; // rcx
  unsigned __int32 v15; // edi
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // r14
  unsigned int *v18; // r9
  struct _BLUETOOTH_SDP_RECORD *v19; // rax
  void *v20; // r8
  Microsoft::Bluetooth::Services::BthServ *v21; // rdi
  struct _BLUETOOTH_SDP_RECORD *v22; // rsi
  Microsoft::Bluetooth::Services::BthServ *v23; // r12
  Microsoft::Bluetooth::Services::BthServ *Record; // rax
  Microsoft::Bluetooth::Services::BthServ *v25; // r15
  struct _BLUETOOTH_SDP_RECORD *v26; // rax
  unsigned int *v27; // r9
  unsigned int v28; // ebp
  bool v29; // zf
  struct _GUID v31; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int32 v32; // [rsp+70h] [rbp+8h] BYREF
  Microsoft::Bluetooth::Services::BthServ *v33; // [rsp+80h] [rbp+18h] BYREF

  v3 = 0;
  if ( !this )
  {
    v6 = 6;
LABEL_41:
    SetLastError(v6);
    return v3;
  }
  if ( *(_DWORD *)a2 != 1480 )
  {
    v6 = 1306;
    goto LABEL_41;
  }
  if ( !*((_QWORD *)this + 1) )
  {
    v6 = 259;
    goto LABEL_41;
  }
  *(_QWORD *)&v31.Data1 = 256;
  *(_QWORD *)v31.Data4 = a2;
  memset_0((char *)a2 + 4, 0, 0x5C4u);
  *(_DWORD *)a2 = 1480;
  v7 = (Microsoft::Bluetooth::Services::BthServ *)*((_QWORD *)this + 1);
  a2[1] = v7;
  v8 = *((_QWORD *)this + 1);
  if ( (unsigned __int8)((*(_BYTE *)v8 >> 3) - 6) <= 1u )
  {
    switch ( *(_BYTE *)v8 & 7 )
    {
      case 5:
        v14 = *(unsigned __int8 *)(v8 + 1);
        v10 = v14 + v8 + 2;
        v9 = v14 + 2;
        break;
      case 6:
        v12 = __ROR2__(*(_WORD *)(v8 + 1), 8);
        v13 = v12;
        v10 = v12 + v8 + 3;
        v9 = v13 + 3;
        break;
      case 7:
        v11 = _byteswap_ulong(*(_DWORD *)(v8 + 1));
        v10 = v8 + v11 + 5LL;
        v9 = v11 + 5;
        break;
      default:
        v10 = 0;
        v9 = 0;
        break;
    }
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  v15 = v8 < v10 ? v9 : 0;
  v16 = v10 & -(__int64)(v8 < v10);
  v17 = v16;
  if ( v16 )
  {
    if ( v16 == *((_QWORD *)this + 2) )
    {
      v17 = 0;
    }
    else if ( v16 > *((_QWORD *)this + 2) )
    {
      v17 = 0;
      v15 = 0;
    }
  }
  *((_DWORD *)a2 + 4) = v15;
  if ( v15 )
  {
    if ( !v7 )
    {
      v6 = 87;
      goto LABEL_41;
    }
    SetLastError(0xDu);
    if ( (*(_BYTE *)v7 & 0xF8) == 0x30 )
    {
      v32 = 0;
      v19 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(
              v7,
              (Microsoft::Bluetooth::Services::BthServ *)((char *)v7 + v15),
              &v32,
              v18);
      v21 = v19;
      if ( v19 )
      {
        v3 = 1;
        v22 = (struct _BLUETOOTH_SDP_RECORD *)((char *)v19 + v32);
        while ( 1 )
        {
          if ( v21 >= v22 )
            goto LABEL_38;
          v23 = v21;
          Record = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(v21, v22, v20);
          v25 = Record;
          if ( !Record )
            break;
          v26 = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(Record, v22, v20);
          v21 = v26;
          if ( !v26 )
            goto LABEL_37;
          v28 = (_DWORD)v26 - (_DWORD)v25;
          if ( (int)v26 - (int)v25 >= v32 )
          {
            v3 = 0;
          }
          else
          {
            if ( (*(_BYTE *)v23 & 0xF8) != 8
              || (LODWORD(v33) = 0,
                  !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(
                                   v23,
                                   v22,
                                   (unsigned __int32 *)&v33,
                                   v27)) )
            {
LABEL_37:
              v3 = 0;
              goto LABEL_38;
            }
            v29 = (unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpNextServiceCallback(
                                  (Microsoft::Bluetooth::Services::BthServ *)(unsigned int)v33,
                                  v25,
                                  (unsigned __int8 *)v28,
                                  &v31) == 0;
LABEL_33:
            if ( v29 )
              goto LABEL_38;
          }
        }
        v29 = v21 == 0;
        goto LABEL_33;
      }
    }
LABEL_38:
    if ( v3 )
      *((_QWORD *)this + 1) = v17;
  }
  return v3;
}

```

## disassembly

```asm
0x180024c84  mov     [rsp+arg_8], rbx
0x180024c89  push    rbp
0x180024c8a  push    rsi
0x180024c8b  push    rdi
0x180024c8c  push    r12
0x180024c8e  push    r13
0x180024c90  push    r14
0x180024c92  push    r15
0x180024c94  sub     rsp, 30h
0x180024c98  xor     ebx, ebx
0x180024c9a  mov     rsi, rdx
0x180024c9d  mov     r13, rcx
0x180024ca0  test    rcx, rcx
0x180024ca3  jnz     short loc_180024CAD
0x180024ca5  lea     ecx, [rbx+6]
0x180024ca8  jmp     loc_180024E8F
0x180024cad  mov     edi, 5C8h
0x180024cb2  cmp     [rdx], edi
0x180024cb4  jz      short loc_180024CC0
0x180024cb6  mov     ecx, 51Ah
0x180024cbb  jmp     loc_180024E8F
0x180024cc0  cmp     [rcx+8], rbx
0x180024cc4  jnz     short loc_180024CD0
0x180024cc6  mov     ecx, 103h
0x180024ccb  jmp     loc_180024E8F
0x180024cd0  and     dword ptr [rsp+68h+var_48+4], ebx
0x180024cd4  lea     rcx, [rdx+4]; void *
0x180024cd8  xor     edx, edx; Val
0x180024cda  mov     dword ptr [rsp+68h+var_48], 100h; void *
0x180024ce2  mov     r8d, 5C4h; Size
0x180024ce8  mov     [rsp+68h+var_40], rsi
0x180024ced  call    memset_0
0x180024cf2  mov     [rsi], edi
0x180024cf4  mov     r15, [r13+8]
0x180024cf8  mov     [rsi+8], r15
0x180024cfc  mov     rdx, [r13+8]
0x180024d00  mov     al, [rdx]
0x180024d02  shr     al, 3
0x180024d05  sub     al, 6
0x180024d07  cmp     al, 1
0x180024d09  jbe     short loc_180024D11
0x180024d0b  xor     ecx, ecx
0x180024d0d  xor     eax, eax
0x180024d0f  jmp     short loc_180024D64
0x180024d11  movzx   ecx, byte ptr [rdx]
0x180024d14  and     ecx, 7
0x180024d17  sub     ecx, 5
0x180024d1a  jz      short loc_180024D56
0x180024d1c  sub     ecx, 1
0x180024d1f  jz      short loc_180024D3F
0x180024d21  cmp     ecx, 1
0x180024d24  jz      short loc_180024D2C
0x180024d26  xor     eax, eax
0x180024d28  xor     ecx, ecx
0x180024d2a  jmp     short loc_180024D64
0x180024d2c  mov     ecx, [rdx+1]
0x180024d2f  bswap   ecx
0x180024d31  mov     eax, ecx
0x180024d33  add     rax, 5
0x180024d37  add     rax, rdx
0x180024d3a  add     ecx, 5
0x180024d3d  jmp     short loc_180024D64
0x180024d3f  movzx   eax, word ptr [rdx+1]
0x180024d43  ror     ax, 8
0x180024d47  movzx   ecx, ax
0x180024d4a  lea     rax, [rdx+3]
0x180024d4e  add     rax, rcx
0x180024d51  add     ecx, 3
0x180024d54  jmp     short loc_180024D64
0x180024d56  movzx   ecx, byte ptr [rdx+1]
0x180024d5a  lea     rax, [rdx+2]
0x180024d5e  add     rax, rcx
0x180024d61  add     ecx, 2
0x180024d64  cmp     rdx, rax
0x180024d67  sbb     edi, edi
0x180024d69  and     edi, ecx
0x180024d6b  cmp     rdx, rax
0x180024d6e  sbb     rcx, rcx
0x180024d71  and     rcx, rax
0x180024d74  mov     r14, rcx
0x180024d77  jz      short loc_180024D8B
0x180024d79  cmp     rcx, [r13+10h]
0x180024d7d  jnz     short loc_180024D84
0x180024d7f  xor     r14d, r14d
0x180024d82  jmp     short loc_180024D8B
0x180024d84  jbe     short loc_180024D8B
0x180024d86  xor     r14d, r14d
0x180024d89  xor     edi, edi
0x180024d8b  mov     [rsi+10h], edi
0x180024d8e  test    edi, edi
0x180024d90  jz      loc_180024E9B
0x180024d96  test    r15, r15
0x180024d99  jz      loc_180024E8A
0x180024d9f  mov     ecx, 0Dh; dwErrCode
0x180024da4  call    cs:__imp_SetLastError
0x180024dab  nop     dword ptr [rax+rax+00h]
0x180024db0  mov     al, [r15]
0x180024db3  and     al, 0F8h
0x180024db5  cmp     al, 30h ; '0'
0x180024db7  jnz     loc_180024E80
0x180024dbd  and     [rsp+68h+arg_0], ebx
0x180024dc1  lea     r8, [rsp+68h+arg_0]; void *
0x180024dc6  mov     edx, edi
0x180024dc8  mov     rcx, r15; this
0x180024dcb  add     rdx, r15; struct _BLUETOOTH_SDP_RECORD *
0x180024dce  call    ?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x180024dd3  mov     rdi, rax
0x180024dd6  test    rax, rax
0x180024dd9  jz      loc_180024E80
0x180024ddf  mov     esi, [rsp+68h+arg_0]
0x180024de3  mov     ebx, 1
0x180024de8  add     rsi, rax
0x180024deb  cmp     rdi, rsi
0x180024dee  jnb     loc_180024E80
0x180024df4  mov     rdx, rsi; struct _BLUETOOTH_SDP_RECORD *
0x180024df7  mov     rcx, rdi; this
0x180024dfa  mov     r12, rdi
0x180024dfd  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x180024e02  mov     r15, rax
0x180024e05  test    rax, rax
0x180024e08  jz      short loc_180024E79
0x180024e0a  mov     rdx, rsi; struct _BLUETOOTH_SDP_RECORD *
0x180024e0d  mov     rcx, rax; this
0x180024e10  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x180024e15  mov     rdi, rax
0x180024e18  test    rax, rax
0x180024e1b  jz      short loc_180024E7E
0x180024e1d  mov     ebp, eax
0x180024e1f  sub     ebp, r15d
0x180024e22  cmp     ebp, [rsp+68h+arg_0]
0x180024e26  jnb     short loc_180024E72
0x180024e28  mov     al, [r12]
0x180024e2c  and     al, 0F8h
0x180024e2e  cmp     al, 8
0x180024e30  jnz     short loc_180024E7E
0x180024e32  and     dword ptr [rsp+68h+arg_10], 0
0x180024e3a  lea     r8, [rsp+68h+arg_10]; void *
0x180024e42  mov     rdx, rsi; struct _BLUETOOTH_SDP_RECORD *
0x180024e45  mov     rcx, r12; this
0x180024e48  call    ?BthpTransposeAndExtendBytes@BthServ@Services@Bluetooth@Microsoft@@YAHPEAU_BLUETOOTH_SDP_RECORD@@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpTransposeAndExtendBytes(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x180024e4d  test    eax, eax
0x180024e4f  jz      short loc_180024E7E
0x180024e51  mov     ecx, dword ptr [rsp+68h+arg_10]; this
0x180024e58  lea     r9, [rsp+68h+var_48]; unsigned int
0x180024e5d  mov     r8d, ebp; unsigned __int8 *
0x180024e60  mov     rdx, r15; unsigned int
0x180024e63  call    ?BthpNextServiceCallback@BthServ@Services@Bluetooth@Microsoft@@YAHKPEAEKPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextServiceCallback(ulong,uchar *,ulong,void *)
0x180024e68  test    eax, eax
0x180024e6a  jnz     loc_180024DEB
0x180024e70  jmp     short loc_180024E80
0x180024e72  xor     ebx, ebx
0x180024e74  jmp     loc_180024DEB
0x180024e79  test    rdi, rdi
0x180024e7c  jmp     short loc_180024E6A
0x180024e7e  xor     ebx, ebx
0x180024e80  test    ebx, ebx
0x180024e82  jz      short loc_180024E9B
0x180024e84  mov     [r13+8], r14
0x180024e88  jmp     short loc_180024E9B
0x180024e8a  mov     ecx, 57h ; 'W'; dwErrCode
0x180024e8f  call    cs:__imp_SetLastError
0x180024e96  nop     dword ptr [rax+rax+00h]
0x180024e9b  mov     eax, ebx
0x180024e9d  mov     rbx, [rsp+68h+arg_8]
0x180024ea2  add     rsp, 30h
0x180024ea6  pop     r15
0x180024ea8  pop     r14
0x180024eaa  pop     r13
0x180024eac  pop     r12
0x180024eae  pop     rdi
0x180024eaf  pop     rsi
0x180024eb0  pop     rbp
0x180024eb1  retn
```
