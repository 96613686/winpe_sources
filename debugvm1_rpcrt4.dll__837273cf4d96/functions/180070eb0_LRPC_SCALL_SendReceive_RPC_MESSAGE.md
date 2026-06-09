# LRPC_SCALL::SendReceive(_RPC_MESSAGE *)

- ea: `0x180070eb0`
- end: `0x1800714f2`
- name: `?SendReceive@LRPC_SCALL@@UEAAJPEAU_RPC_MESSAGE@@@Z`
- size: `1602`
- prototype: `int(LRPC_SCALL *__hidden this, struct _RPC_MESSAGE *)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, installer_update`

## callees

- `0x180018484`
- `0x1800193a8`
- `0x1800206a0`
- `0x180021ce0`
- `0x180025130`
- `0x180025280`
- `0x180026ca0`
- `0x1800283bc`
- `0x180070eb0`
- `0x1800714f8`
- `0x18007159c`
- `0x180071640`
- `0x1800716d8`
- `0x180071d20`
- `0x180072804`
- `0x1800951bc`
- `0x1800ca031`
- `0x1800ca140`

## import_xrefs

- `ntdll!NtAlpcDeleteSectionView` at `0x18007139f`
- `ntdll!NtAlpcDeleteSectionView` at `0x18007139f`
- `ntdll!NtAlpcDeletePortSection` at `0x1800714e7`
- `ntdll!NtAlpcDeletePortSection` at `0x1800714e7`

## pseudocode

```c
__int64 __fastcall LRPC_SCALL::SendReceive(LRPC_SCALL *this, struct _RPC_MESSAGE *a2)
{
  void *v4; // r15
  int v5; // ebx
  ULONG Flags; // r12d
  __int64 result; // rax
  BCACHE *v8; // rcx
  ULONG v9; // r12d
  unsigned __int64 v10; // rdx
  struct _PORT_MESSAGE *v11; // r14
  unsigned int BufferLength; // eax
  __int16 v13; // si
  size_t v14; // rbx
  unsigned int v15; // ebx
  unsigned __int64 v16; // r8
  unsigned int HeaderSize; // eax
  unsigned int v18; // edx
  SIZE_T v19; // r10
  void *v20; // r12
  int v21; // ecx
  __int16 v22; // ax
  PRTL_CRITICAL_SECTION v23; // rcx
  int v24; // eax
  int *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  struct RPC_DISPATCH_TABLE *v28; // r9
  unsigned int v29; // esi
  unsigned __int64 v30; // rdx
  _OWORD *v31; // rsi
  __int64 v32; // rax
  int v33; // ebx
  int v34; // edx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rcx
  unsigned int v38; // eax
  __int64 v39; // rbx
  const void *v40; // rdx
  __int64 v41; // rcx
  void *v42; // rdx
  unsigned int v43; // eax
  __int64 v44; // rbx
  struct _PORT_MESSAGE *v45; // [rsp+20h] [rbp-A9h]
  unsigned __int64 *v46; // [rsp+28h] [rbp-A1h]
  struct LRPC_SYSTEM_HANDLE_DATA *v47; // [rsp+30h] [rbp-99h]
  union _LARGE_INTEGER *v48; // [rsp+38h] [rbp-91h]
  void *v49; // [rsp+50h] [rbp-79h] BYREF
  void *v50; // [rsp+58h] [rbp-71h] BYREF
  void *v51; // [rsp+60h] [rbp-69h] BYREF
  _DWORD v52[6]; // [rsp+68h] [rbp-61h] BYREF
  _DWORD v53[24]; // [rsp+80h] [rbp-49h] BYREF

  v50 = 0;
  v49 = 0;
  v51 = 0;
  v4 = 0;
  v5 = *((_DWORD *)this + 58);
  Flags = NtCurrentPeb()->ProcessParameters->Flags;
  result = LRPC_SCALL::PrepareForCallbackIfNecessary(this);
  if ( !(_DWORD)result )
  {
    v9 = Flags >> 31;
    if ( (v5 & 0x40) != 0 )
      goto LABEL_3;
    v30 = 65280;
    if ( !v9 )
      v30 = 4096;
    v31 = BCACHE::Allocate(v8, v30);
    if ( v31 )
    {
      v32 = *((_QWORD *)this + 56);
      *v31 = *(_OWORD *)v32;
      v31[1] = *(_OWORD *)(v32 + 16);
      *((_QWORD *)v31 + 4) = *(_QWORD *)(v32 + 32);
      *((_QWORD *)v31 + 5) = 6;
      *((_DWORD *)v31 + 13) = *((_DWORD *)this + 133);
      *((_DWORD *)v31 + 12) = 0;
      if ( (*((_DWORD *)this + 58) & 0x20) != 0 && (*((_DWORD *)this + 58) & 0x1000) == 0 )
      {
        *(_QWORD *)(*((_QWORD *)this + 74) + 208LL) = *((_QWORD *)this + 44);
        _InterlockedOr((volatile signed __int32 *)this + 58, 0x4000u);
      }
      *(_DWORD *)(*((_QWORD *)this + 74) + 224LL) = 1;
      v33 = LRPC_ADDRESS::AlpcSend(
              *(LRPC_ADDRESS **)(*((_QWORD *)this + 38) + 56LL),
              (struct _PORT_MESSAGE *)v31,
              0,
              0,
              0,
              0,
              0);
      I_RpcBCacheFree(v31);
      if ( v33 < 0 )
      {
        return 1727;
      }
      else
      {
        SEMAPHORE_EVENT::Wait((SEMAPHORE_EVENT *)(*((_QWORD *)this + 74) + 16LL), v34);
        *(_DWORD *)(*((_QWORD *)this + 74) + 224LL) = 2;
        v35 = *((_QWORD *)this + 74);
        v29 = *(_DWORD *)(v35 + 28);
        if ( !v29 )
        {
          v36 = *(_QWORD *)(v35 + 32);
          v37 = *((_QWORD *)this + 56);
          *(_OWORD *)v37 = *(_OWORD *)v36;
          *(_OWORD *)(v37 + 16) = *(_OWORD *)(v36 + 16);
          *(_QWORD *)(v37 + 32) = *(_QWORD *)(v36 + 32);
          LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(
            *(LRPC_ADDRESS **)(*((_QWORD *)this + 38) + 56LL),
            *(void **)(*((_QWORD *)this + 74) + 32LL));
          *(_QWORD *)(*((_QWORD *)this + 74) + 32LL) = 0;
LABEL_3:
          v10 = 65280;
          ++*(_DWORD *)(*((_QWORD *)this + 74) + 8LL);
          if ( !v9 )
            v10 = 4096;
          v11 = (struct _PORT_MESSAGE *)BCACHE::Allocate(v8, v10);
          if ( !v11 )
          {
            v29 = 14;
            v20 = 0;
LABEL_48:
            --*(_DWORD *)(*((_QWORD *)this + 74) + 8LL);
            if ( v4 )
            {
              v39 = *((_QWORD *)this + 38);
              LogEvent(0x4Cu, 0x44u, *(void **)(v39 + 48), v4, 1u, (int)v46, (int)v47);
              NtAlpcDeleteSectionView(*(_QWORD *)(v39 + 48), 0, v4);
            }
            goto LABEL_28;
          }
          BufferLength = a2->BufferLength;
          v13 = 72;
          if ( v9 )
          {
            if ( BufferLength <= 0xFE98 )
              memcpy_0(&v11[2].MessageId, (const void *)(*((_QWORD *)this + 56) + 64LL), a2->BufferLength);
          }
          else
          {
            v14 = BufferLength;
            if ( BufferLength > 0xF98 )
            {
              v38 = AlpcAllocateSectionAndView(
                      *(void **)(*((_QWORD *)this + 38) + 48LL),
                      BufferLength,
                      &v51,
                      &v50,
                      (unsigned __int64 *)&v49);
              v4 = v50;
              v29 = v38;
              if ( v38 )
              {
                v20 = v51;
                goto LABEL_48;
              }
              v40 = (const void *)*((_QWORD *)this + 58);
              if ( v40 )
              {
                memcpy_0(v50, v40, v14);
                LRPC_ADDRESS::AlpcFreeSection(*(LRPC_ADDRESS **)(*((_QWORD *)this + 38) + 56LL), *((void **)this + 57));
                v41 = *((_QWORD *)this + 38);
                v42 = (void *)*((_QWORD *)this + 58);
                *((_QWORD *)this + 57) = 0;
                LRPC_ADDRESS::AlpcFreeView(*(LRPC_ADDRESS **)(v41 + 56), v42);
                *((_QWORD *)this + 58) = 0;
              }
              else
              {
                memcpy_0(v50, (const void *)(*((_QWORD *)this + 56) + 64LL), v14);
              }
              v13 = 72;
              v49 = v51;
            }
            else
            {
              memcpy_0(&v11[2].MessageId, (const void *)(*((_QWORD *)this + 56) + 64LL), BufferLength);
            }
            if ( v4 )
            {
              v15 = 1610612736;
              v16 = 72;
              goto LABEL_14;
            }
          }
          v15 = 0x20000000;
          v16 = 40;
LABEL_14:
          RpcpAlpcInitializeMessageAttribute(
            v15,
            (struct RPCP_ALPC_MESSAGE_ATTRIBUTES *)v53,
            v16,
            (unsigned __int64 *)&v50);
          HeaderSize = RpcpAlpcpGetHeaderSize(v53[0] & 0xC0000000);
          v19 = 0;
          *(_QWORD *)((char *)&v53[2] + HeaderSize) = this;
          *(_QWORD *)((char *)v53 + HeaderSize) = 0;
          if ( v4 )
          {
            v43 = RpcpAlpcpGetHeaderSize(v53[0] & 0x80000000);
            v20 = v49;
            *(_DWORD *)((char *)v53 + v43) = 393216;
            *(_QWORD *)((char *)&v53[2] + v43) = v20;
            *(_QWORD *)((char *)&v53[4] + v43) = v4;
            *(_QWORD *)((char *)&v53[6] + v43) = a2->BufferLength;
          }
          else
          {
            v20 = v49;
          }
          v53[1] = v15;
          *(_OWORD *)&v11->u1.s1.DataLength = 0;
          *(union _PORT_MESSAGE::$C6BC508B531A81D74C33985719C23F49 *)((char *)&v11->8 + 8) = 0;
          v11->ClientViewSize = 0;
          if ( v4 )
          {
            v11->u1.s1.DataLength = 72;
            v21 = 4;
            *(_QWORD *)&v11[2].MessageId = a2->BufferLength;
          }
          else
          {
            v21 = v19;
            v22 = LOWORD(a2->BufferLength) + 64;
            v11->u1.s1.DataLength = v22;
            v13 = v22;
          }
          LODWORD(v11[1].DoNotUseThisField) = v21;
          v11->u2.s2.Type = 0x4000;
          v11->u1.s1.TotalLength = v13 + 40;
          *(_QWORD *)&v11[1].u1.s1.DataLength = 9;
          *((_DWORD *)&v11[1].DoNotUseThisField + 2) = *(unsigned __int16 *)(*((_QWORD *)this + 39) + 8LL);
          v23 = GlobalRpcServer;
          *((_DWORD *)&v11[1].DoNotUseThisField + 3) = a2->ProcNum;
          HIDWORD(v11[1].DoNotUseThisField) = *((_DWORD *)this + 133);
          v11[1].MessageId = v19;
          v11[1].ClientViewSize = v19;
          v11[2].u1.Length = v19;
          ++LODWORD(v23[1].OwningThread);
          v24 = LRPC_SASSOCIATION::AlpcSendWaitReceivePort(
                  *((LRPC_SASSOCIATION **)this + 38),
                  v18,
                  v11,
                  (struct _ALPC_MESSAGE_ATTRIBUTES *)v53,
                  v45,
                  v46,
                  v47,
                  v48);
          if ( v24 != -1073741801 )
          {
            if ( v24 == -1073741769 )
              goto LABEL_60;
            if ( v24 != -1073741756 && v24 != -1073741670 )
            {
              switch ( v24 )
              {
                case -1073740031:
                  goto LABEL_59;
                case 0:
                  a2->DataRepresentation = 16;
                  v25 = (int *)*((_QWORD *)this + 39);
                  v26 = *(_QWORD *)v25;
                  if ( (*(_DWORD *)(*(_QWORD *)v25 + 168LL) & 0x2000000) != 0 )
                  {
                    v27 = *(_QWORD *)(v26 + 176) + 80LL * v25[3];
                    a2->TransferSyntax = (PRPC_SYNTAX_IDENTIFIER)v27;
                    v28 = *(struct RPC_DISPATCH_TABLE **)(v27 + 24);
                    if ( v28 )
                    {
LABEL_27:
                      v29 = LRPC_CALLBACK::SendReceiveLoop(
                              *((LRPC_CALLBACK **)this + 74),
                              0,
                              (struct _RPC_SYNTAX_IDENTIFIER *)v27,
                              v28,
                              a2,
                              (unsigned int)v46,
                              *((_DWORD *)this + 128),
                              (LRPC_SCALL *)((char *)this + 516),
                              *((struct LRPC_SBINDING **)this + 39));
LABEL_28:
                      if ( v20 )
                      {
                        v44 = *((_QWORD *)this + 38);
                        LogEvent(0x4Cu, 0x44u, *(void **)(v44 + 48), v20, 0, (int)v46, (int)v47);
                        NtAlpcDeletePortSection(*(_QWORD *)(v44 + 48), 0, v20);
                      }
                      if ( v11 )
                        I_RpcBCacheFree(v11);
                      return v29;
                    }
                  }
                  else
                  {
                    v27 = v26 + 104;
                    a2->TransferSyntax = (PRPC_SYNTAX_IDENTIFIER)(v26 + 104);
                  }
                  v28 = *(struct RPC_DISPATCH_TABLE **)(v26 + 128);
                  goto LABEL_27;
                case 258:
LABEL_59:
                  v29 = 1818;
LABEL_47:
                  v52[2] = v24;
                  v52[0] = 3;
                  RpcpErrorAddRecord(2u, v29, 0x500u, 1, (struct tagParam *)v52);
                  goto LABEL_48;
              }
LABEL_60:
              v29 = 1726;
              goto LABEL_47;
            }
          }
          v29 = 14;
          goto LABEL_47;
        }
      }
    }
    else
    {
      return 14;
    }
    return v29;
  }
  return result;
}

```

## disassembly

```asm
0x180070eb0  mov     [rsp-8+arg_10], rbx
0x180070eb5  push    rbp
0x180070eb6  push    rsi
0x180070eb7  push    rdi
0x180070eb8  push    r12
0x180070eba  push    r13
0x180070ebc  push    r14
0x180070ebe  push    r15
0x180070ec0  lea     rbp, [rsp-27h]
0x180070ec5  sub     rsp, 0F0h
0x180070ecc  mov     rax, cs:__security_cookie
0x180070ed3  xor     rax, rsp
0x180070ed6  mov     [rbp+57h+var_40], rax
0x180070eda  xor     r14d, r14d
0x180070edd  mov     r13, rdx
0x180070ee0  mov     eax, r14d
0x180070ee3  mov     [rbp+57h+var_C8], r14
0x180070ee7  mov     [rbp+57h+var_D0], rax
0x180070eeb  mov     rdi, rcx
0x180070eee  mov     [rbp+57h+var_C0], rax
0x180070ef2  mov     r15d, r14d
0x180070ef5  mov     rax, gs:60h
0x180070efe  mov     ebx, [rcx+0E8h]
0x180070f04  mov     r8, [rax+20h]
0x180070f08  mov     r12d, [r8+8]
0x180070f0c  call    ?PrepareForCallbackIfNecessary@LRPC_SCALL@@AEAAJXZ; LRPC_SCALL::PrepareForCallbackIfNecessary(void)
0x180070f11  test    eax, eax
0x180070f13  jnz     loc_180071154
0x180070f19  shr     r12d, 1Fh
0x180070f1d  test    bl, 40h
0x180070f20  jz      loc_18007117B
0x180070f26  mov     rax, [rdi+250h]
0x180070f2d  mov     edx, 0FF00h
0x180070f32  inc     dword ptr [rax+8]
0x180070f35  test    r12d, r12d
0x180070f38  jnz     short loc_180070F3F
0x180070f3a  mov     edx, 1000h; unsigned __int64
0x180070f3f  call    ?Allocate@BCACHE@@QEAAPEAX_K@Z; BCACHE::Allocate(unsigned __int64)
0x180070f44  mov     r14, rax
0x180070f47  test    rax, rax
0x180070f4a  jz      loc_1800713BE
0x180070f50  mov     eax, [r13+18h]
0x180070f54  mov     esi, 48h ; 'H'
0x180070f59  test    r12d, r12d
0x180070f5c  jnz     short loc_180070F91
0x180070f5e  mov     ebx, eax
0x180070f60  cmp     eax, 0F98h
0x180070f65  ja      loc_180071301
0x180070f6b  mov     rdx, [rdi+1C0h]
0x180070f72  lea     rcx, [r14+68h]; void *
0x180070f76  add     rdx, 40h ; '@'; Src
0x180070f7a  mov     r8d, eax; Size
0x180070f7d  call    memcpy_0
0x180070f82  test    r15, r15
0x180070f85  jz      short loc_180070F9C
0x180070f87  mov     ebx, 60000000h
0x180070f8c  mov     r8, rsi
0x180070f8f  jmp     short loc_180070FA7
0x180070f91  cmp     eax, 0FE98h
0x180070f96  jbe     loc_1800713C8
0x180070f9c  mov     ebx, 20000000h
0x180070fa1  mov     r8d, 28h ; '('; unsigned __int64
0x180070fa7  lea     r9, [rbp+57h+var_C8]; unsigned __int64 *
0x180070fab  mov     ecx, ebx; unsigned int
0x180070fad  lea     rdx, [rbp+57h+var_A0]; struct RPCP_ALPC_MESSAGE_ATTRIBUTES *
0x180070fb1  call    ?RpcpAlpcInitializeMessageAttribute@@YAJKPEAVRPCP_ALPC_MESSAGE_ATTRIBUTES@@_KPEA_K@Z; RpcpAlpcInitializeMessageAttribute(ulong,RPCP_ALPC_MESSAGE_ATTRIBUTES *,unsigned __int64,unsigned __int64 *)
0x180070fb6  mov     ecx, dword ptr [rbp+57h+var_A0]
0x180070fb9  and     ecx, 0C0000000h; unsigned int
0x180070fbf  call    ?RpcpAlpcpGetHeaderSize@@YAKK@Z; RpcpAlpcpGetHeaderSize(ulong)
0x180070fc4  mov     r9d, eax
0x180070fc7  xor     r10d, r10d
0x180070fca  mov     [rbp+r9+57h+var_98], rdi
0x180070fcf  mov     [rbp+r9+57h+var_A0], r10
0x180070fd4  test    r15, r15
0x180070fd7  jnz     loc_180071463
0x180070fdd  mov     r12, [rbp+57h+var_D0]
0x180070fe1  mov     dword ptr [rbp+57h+var_A0+4], ebx
0x180070fe4  xorps   xmm0, xmm0
0x180070fe7  xor     eax, eax
0x180070fe9  movups  xmmword ptr [r14], xmm0
0x180070fed  movups  xmmword ptr [r14+10h], xmm0
0x180070ff2  mov     [r14+20h], rax
0x180070ff6  test    r15, r15
0x180070ff9  jnz     loc_1800712EB
0x180070fff  movzx   eax, word ptr [r13+18h]
0x180071004  mov     ecx, r10d
0x180071007  add     ax, 40h ; '@'
0x18007100b  mov     [r14], ax
0x18007100f  movzx   esi, ax
0x180071012  mov     [r14+30h], ecx
0x180071016  lea     r9, [rbp+57h+var_A0]; struct _ALPC_MESSAGE_ATTRIBUTES *
0x18007101a  mov     word ptr [r14+4], 4000h
0x180071021  add     si, 28h ; '('
0x180071025  mov     [r14+2], si
0x18007102a  mov     r8, r14; struct _PORT_MESSAGE *
0x18007102d  mov     qword ptr [r14+28h], 9
0x180071035  mov     rax, [rdi+138h]
0x18007103c  movzx   ecx, word ptr [rax+8]
0x180071040  mov     [r14+38h], ecx
0x180071044  mov     eax, [r13+1Ch]
0x180071048  mov     rcx, cs:?GlobalRpcServer@@3PEAVRPC_SERVER@@EA; RPC_SERVER * GlobalRpcServer
0x18007104f  mov     [r14+3Ch], eax
0x180071053  mov     eax, [rdi+214h]
0x180071059  mov     [r14+34h], eax
0x18007105d  mov     [r14+40h], r10d
0x180071061  mov     [r14+48h], r10
0x180071065  mov     [r14+50h], r10d
0x180071069  mov     eax, [rcx+38h]
0x18007106c  inc     eax
0x18007106e  mov     [rcx+38h], eax
0x180071071  mov     rcx, [rdi+130h]; this
0x180071078  call    ?AlpcSendWaitReceivePort@LRPC_SASSOCIATION@@QEAAJKPEAU_PORT_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@0PEA_K1PEAT_LARGE_INTEGER@@@Z; LRPC_SASSOCIATION::AlpcSendWaitReceivePort(ulong,_PORT_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *,unsigned __int64 *,_ALPC_MESSAGE_ATTRIBUTES *,_LARGE_INTEGER *)
0x18007107d  cmp     eax, 0C0000017h
0x180071082  jz      loc_1800714B4
0x180071088  cmp     eax, 0C0000037h
0x18007108d  jz      loc_1800714AA
0x180071093  cmp     eax, 0C0000044h
0x180071098  jz      loc_1800714B4
0x18007109e  cmp     eax, 0C000009Ah
0x1800710a3  jz      loc_1800714B4
0x1800710a9  cmp     eax, 0C0000701h
0x1800710ae  jz      loc_1800714A0
0x1800710b4  test    eax, eax
0x1800710b6  jnz     loc_180071499
0x1800710bc  mov     dword ptr [r13+8], 10h
0x1800710c4  mov     rax, [rdi+138h]
0x1800710cb  mov     rdx, [rax]
0x1800710ce  test    dword ptr [rdx+0A8h], 2000000h
0x1800710d8  jz      loc_1800712A9
0x1800710de  movsxd  rax, dword ptr [rax+0Ch]
0x1800710e2  lea     r8, [rax+rax*4]
0x1800710e6  shl     r8, 4
0x1800710ea  add     r8, [rdx+0B0h]; struct _RPC_SYNTAX_IDENTIFIER *
0x1800710f1  mov     [r13+20h], r8
0x1800710f5  mov     r9, [r8+18h]
0x1800710f9  test    r9, r9
0x1800710fc  jnz     short loc_180071105
0x1800710fe  mov     r9, [rdx+80h]; struct RPC_DISPATCH_TABLE *
0x180071105  mov     rax, [rdi+138h]
0x18007110c  lea     rcx, [rdi+204h]
0x180071113  mov     [rsp+120h+var_E0], rax; struct LRPC_SBINDING *
0x180071118  xor     edx, edx; int
0x18007111a  mov     eax, [rdi+200h]
0x180071120  mov     [rsp+120h+var_E8], rcx; struct RPC_UUID *
0x180071125  mov     rcx, [rdi+250h]; this
0x18007112c  mov     dword ptr [rsp+120h+var_F0], eax; int
0x180071130  mov     [rsp+120h+var_100], r13; struct _RPC_MESSAGE *
0x180071135  call    ?SendReceiveLoop@LRPC_CALLBACK@@QEAAJHPEAU_RPC_SYNTAX_IDENTIFIER@@PEAURPC_DISPATCH_TABLE@@PEAU_RPC_MESSAGE@@KHPEAVRPC_UUID@@PEAVLRPC_SBINDING@@@Z; LRPC_CALLBACK::SendReceiveLoop(int,_RPC_SYNTAX_IDENTIFIER *,RPC_DISPATCH_TABLE *,_RPC_MESSAGE *,ulong,int,RPC_UUID *,LRPC_SBINDING *)
0x18007113a  mov     esi, eax
0x18007113c  test    r12, r12
0x18007113f  jnz     loc_1800714BE
0x180071145  test    r14, r14
0x180071148  jz      short loc_180071152
0x18007114a  mov     rcx, r14; void *
0x18007114d  call    I_RpcBCacheFree
0x180071152  mov     eax, esi
0x180071154  mov     rcx, [rbp+57h+var_40]
0x180071158  xor     rcx, rsp; StackCookie
0x18007115b  call    __security_check_cookie
0x180071160  mov     rbx, [rsp+120h+arg_10]
0x180071168  add     rsp, 0F0h
0x18007116f  pop     r15
0x180071171  pop     r14
0x180071173  pop     r13
0x180071175  pop     r12
0x180071177  pop     rdi
0x180071178  pop     rsi
0x180071179  pop     rbp
0x18007117a  retn
0x18007117b  mov     edx, 0FF00h
0x180071180  test    r12d, r12d
0x180071183  jnz     short loc_18007118A
0x180071185  mov     edx, 1000h; unsigned __int64
0x18007118a  call    ?Allocate@BCACHE@@QEAAPEAX_K@Z; BCACHE::Allocate(unsigned __int64)
0x18007118f  mov     rsi, rax
0x180071192  test    rax, rax
0x180071195  jz      loc_1800713AA
0x18007119b  mov     rax, [rdi+1C0h]
0x1800711a2  movups  xmm0, xmmword ptr [rax]
0x1800711a5  movups  xmmword ptr [rsi], xmm0
0x1800711a8  movups  xmm1, xmmword ptr [rax+10h]
0x1800711ac  movups  xmmword ptr [rsi+10h], xmm1
0x1800711b0  movsd   xmm0, qword ptr [rax+20h]
0x1800711b5  movsd   qword ptr [rsi+20h], xmm0
0x1800711ba  mov     qword ptr [rsi+28h], 6
0x1800711c2  mov     eax, [rdi+214h]
0x1800711c8  mov     [rsi+34h], eax
0x1800711cb  mov     [rsi+30h], r14d
0x1800711cf  mov     eax, [rdi+0E8h]
0x1800711d5  test    al, 20h
0x1800711d7  jnz     loc_1800712B6
0x1800711dd  mov     rax, [rdi+250h]
0x1800711e4  xor     r9d, r9d; void *
0x1800711e7  mov     [rsp+120h+var_F0], r14; struct LRPC_SYSTEM_HANDLE_DATA *
0x1800711ec  xor     r8d, r8d; int
0x1800711ef  mov     [rsp+120h+var_F8], r14; unsigned __int64
0x1800711f4  mov     rdx, rsi; struct _PORT_MESSAGE *
0x1800711f7  mov     [rsp+120h+var_100], r14; void *
0x1800711fc  mov     dword ptr [rax+0E0h], 1
0x180071206  mov     rcx, [rdi+130h]
0x18007120d  mov     rcx, [rcx+38h]; this
0x180071211  call    ?AlpcSend@LRPC_ADDRESS@@QEAAJPEAU_PORT_MESSAGE@@HPEAX1_KPEAVLRPC_SYSTEM_HANDLE_DATA@@@Z; LRPC_ADDRESS::AlpcSend(_PORT_MESSAGE *,int,void *,void *,unsigned __int64,LRPC_SYSTEM_HANDLE_DATA *)
0x180071216  mov     rcx, rsi; void *
0x180071219  mov     ebx, eax
0x18007121b  call    I_RpcBCacheFree
0x180071220  test    ebx, ebx
0x180071222  js      loc_1800713B4
0x180071228  mov     rcx, [rdi+250h]
0x18007122f  add     rcx, 10h; this
0x180071233  call    ?Wait@SEMAPHORE_EVENT@@QEAAHJ@Z; SEMAPHORE_EVENT::Wait(long)
0x180071238  mov     rax, [rdi+250h]
0x18007123f  mov     dword ptr [rax+0E0h], 2
0x180071249  mov     rax, [rdi+250h]
0x180071250  mov     esi, [rax+1Ch]
0x180071253  test    esi, esi
0x180071255  jnz     loc_180071152
0x18007125b  mov     rax, [rax+20h]
0x18007125f  mov     rcx, [rdi+1C0h]
0x180071266  movups  xmm0, xmmword ptr [rax]
0x180071269  movups  xmmword ptr [rcx], xmm0
0x18007126c  movups  xmm1, xmmword ptr [rax+10h]
0x180071270  movups  xmmword ptr [rcx+10h], xmm1
0x180071274  movsd   xmm0, qword ptr [rax+20h]
0x180071279  movsd   qword ptr [rcx+20h], xmm0
0x18007127e  mov     rdx, [rdi+250h]
0x180071285  mov     rcx, [rdi+130h]
0x18007128c  mov     rdx, [rdx+20h]; void *
0x180071290  mov     rcx, [rcx+38h]; this
0x180071294  call    ?RpcFreeLrpcAddressBuffer@LRPC_ADDRESS@@QEAAXPEAX@Z; LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(void *)
0x180071299  mov     rax, [rdi+250h]
0x1800712a0  mov     [rax+20h], r14
0x1800712a4  jmp     loc_180070F26
0x1800712a9  lea     r8, [rdx+68h]
0x1800712ad  mov     [r13+20h], r8
0x1800712b1  jmp     loc_1800710FE
0x1800712b6  mov     eax, [rdi+0E8h]
0x1800712bc  bt      eax, 0Ch
0x1800712c0  jb      loc_1800711DD
0x1800712c6  mov     rcx, [rdi+250h]
0x1800712cd  mov     rax, [rdi+160h]
0x1800712d4  mov     [rcx+0D0h], rax
0x1800712db  lock or dword ptr [rdi+0E8h], 4000h
0x1800712e6  jmp     loc_1800711DD
0x1800712eb  mov     [r14], si
0x1800712ef  mov     ecx, 4
0x1800712f4  mov     eax, [r13+18h]
0x1800712f8  mov     [r14+68h], rax
0x1800712fc  jmp     loc_180071012
0x180071301  mov     rcx, [rdi+130h]
0x180071308  lea     rax, [rbp+57h+var_D0]
0x18007130c  lea     r9, [rbp+57h+var_C8]; void **
0x180071310  mov     [rsp+120h+var_100], rax; unsigned __int64 *
0x180071315  lea     r8, [rbp+57h+var_C0]; void **
0x180071319  mov     rdx, rbx; unsigned __int64
0x18007131c  mov     rcx, [rcx+30h]; void *
0x180071320  call    ?AlpcAllocateSectionAndView@@YAJPEAX_KPEAPEAX2PEA_K@Z; AlpcAllocateSectionAndView(void *,unsigned __int64,void * *,void * *,unsigned __int64 *)
0x180071325  mov     r15, [rbp+57h+var_C8]
0x180071329  mov     esi, eax
0x18007132b  test    eax, eax
0x18007132d  jz      loc_1800713E4
0x180071333  mov     r12, [rbp+57h+var_C0]
0x180071337  jmp     short loc_180071363
0x180071339  mov     r9d, 1; int
0x18007133f  mov     [rbp+57h+var_B0], eax
0x180071342  lea     rax, [rbp+57h+var_B8]
0x180071346  mov     [rbp+57h+var_B8], 3
0x18007134d  mov     r8d, 500h; unsigned __int16
0x180071353  mov     [rsp+120h+var_100], rax; struct tagParam *
0x180071358  mov     edx, esi; int
0x18007135a  lea     ecx, [r9+1]; unsigned int
0x18007135e  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180071363  mov     rax, [rdi+250h]
0x18007136a  dec     dword ptr [rax+8]
0x18007136d  test    r15, r15
0x180071370  jz      loc_18007113C
0x180071376  mov     rbx, [rdi+130h]
0x18007137d  mov     r9, r15; void *
0x180071380  mov     dl, 44h ; 'D'; unsigned __int8
0x180071382  mov     [rsp+120h+var_100], 1; unsigned __int64
0x18007138b  mov     cl, 4Ch ; 'L'; unsigned __int8
0x18007138d  mov     r8, [rbx+30h]; void *
0x180071391  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180071396  mov     rcx, [rbx+30h]
0x18007139a  mov     r8, r15
0x18007139d  xor     edx, edx
0x18007139f  call    cs:__imp_NtAlpcDeleteSectionView
0x1800713a5  jmp     loc_18007113C
0x1800713aa  mov     esi, 0Eh
0x1800713af  jmp     loc_180071152
0x1800713b4  mov     esi, 6BFh
0x1800713b9  jmp     loc_180071152
0x1800713be  mov     esi, 0Eh
0x1800713c3  mov     r12, r15
0x1800713c6  jmp     short loc_180071363
0x1800713c8  mov     rdx, [rdi+1C0h]
0x1800713cf  lea     rcx, [r14+68h]; void *
0x1800713d3  add     rdx, 40h ; '@'; Src
0x1800713d7  mov     r8, rax; Size
0x1800713da  call    memcpy_0
0x1800713df  jmp     loc_180070F9C
  ... truncated ...
```
