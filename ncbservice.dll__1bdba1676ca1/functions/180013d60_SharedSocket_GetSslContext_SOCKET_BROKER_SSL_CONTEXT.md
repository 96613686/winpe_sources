# SharedSocket::GetSslContext(_SOCKET_BROKER_SSL_CONTEXT * *)

- ea: `0x180013d60`
- end: `0x180013efc`
- name: `?GetSslContext@SharedSocket@@AEAAKPEAPEAU_SOCKET_BROKER_SSL_CONTEXT@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(SharedSocket *this, struct _SOCKET_BROKER_SSL_CONTEXT **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013f04`

## callees

- `0x18000a0a0`
- `0x180012900`
- `0x180013d60`
- `0x1800140d8`
- `0x180014130`
- `0x180032108`
- `0x180033010`

## import_xrefs

- `SspiCli!FreeContextBuffer` at `0x180013ef1`
- `SspiCli!FreeContextBuffer` at `0x180013ef1`

## string_xrefs

- `0x180013e39`: `SharedSocket:GetSslContext copy string for package name failed`
- `0x180013e06`: `SharedSocket:GetSslContext ExportSecurityContext failed`
- `0x180013df7`: `SharedSocket:GetSslContext Allocating Exported security context buffer failed`

## pseudocode

```c
__int64 __fastcall SharedSocket::GetSslContext(SharedSocket *this, struct _SOCKET_BROKER_SSL_CONTEXT **a2)
{
  unsigned int v2; // ebx
  char *v3; // r14
  bool v4; // zf
  struct _SOCKET_BROKER_SSL_CONTEXT *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  struct _SOCKET_BROKER_SSL_CONTEXT *v11; // rsi
  const wchar_t *v12; // r8
  __int64 v13; // r9
  unsigned int v14; // eax
  unsigned int v15; // eax
  void *v16; // rax
  size_t v17; // r8
  const void *v18; // rdx
  void *Src[2]; // [rsp+30h] [rbp-18h] BYREF
  struct _SOCKET_BROKER_SSL_CONTEXT *v20; // [rsp+80h] [rbp+38h] BYREF

  v2 = 0;
  v20 = 0;
  v3 = (char *)this + 144;
  *a2 = 0;
  v4 = *((_QWORD *)this + 18) == -1;
  *(_OWORD *)Src = 0;
  if ( !v4 && *((_QWORD *)this + 19) != -1 && *((_QWORD *)this + 17) )
  {
    v8 = (struct _SOCKET_BROKER_SSL_CONTEXT *)MALLOC(0x30u);
    v20 = v8;
    v11 = v8;
    if ( !v8 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
        goto LABEL_2;
      v12 = L"SharedSocket:GetSslContext AllocatedSslContext failed";
      goto LABEL_10;
    }
    v14 = NcbUtilsAllocCopyString(*((_QWORD *)this + 17), v8);
    v2 = v14;
    if ( v14 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v13 = v14;
        v12 = L"SharedSocket:GetSslContext copy string for package name failed";
        goto LABEL_11;
      }
    }
    else
    {
      v15 = (*(__int64 (__fastcall **)(char *, _QWORD, void **, _QWORD))(*((_QWORD *)this + 27) + 160LL))(v3, 0, Src, 0);
      v2 = v15;
      if ( v15 )
      {
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          v13 = v15;
          v12 = L"SharedSocket:GetSslContext ExportSecurityContext failed";
          goto LABEL_11;
        }
      }
      else
      {
        v16 = MALLOC(LODWORD(Src[0]));
        *((_QWORD *)v11 + 2) = v16;
        if ( v16 )
        {
          *((void **)v11 + 1) = Src[0];
          *(_OWORD *)((char *)v11 + 24) = *((_OWORD *)this + 10);
          *((_QWORD *)v11 + 5) = *((_QWORD *)this + 22);
          v17 = LODWORD(Src[0]);
          v18 = Src[1];
          *((_OWORD *)this + 10) = 0;
          *((_QWORD *)this + 22) = 0;
          memcpy_0(*((void **)v11 + 2), v18, v17);
          *a2 = v11;
          v20 = 0;
        }
        else if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          v12 = L"SharedSocket:GetSslContext Allocating Exported security context buffer failed";
LABEL_10:
          v13 = 0;
LABEL_11:
          McTemplateU0zq_EventWriteTransfer(v10, v9, v12, v13);
        }
      }
    }
  }
LABEL_2:
  SharedSocket::FreeSocketBrokerSslContext(&v20);
  if ( Src[1] )
    FreeContextBuffer(Src[1]);
  return v2;
}

```

## disassembly

```asm
0x180013d60  push    rbp
0x180013d62  push    rbx
0x180013d63  push    rsi
0x180013d64  push    rdi
0x180013d65  push    r14
0x180013d67  push    r15
0x180013d69  mov     rbp, rsp
0x180013d6c  sub     rsp, 48h
0x180013d70  xor     ebx, ebx
0x180013d72  mov     [rbp+arg_0], 0
0x180013d7a  lea     r14, [rcx+90h]
0x180013d81  mov     [rdx], rbx
0x180013d84  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180013d88  xorps   xmm0, xmm0
0x180013d8b  mov     r15, rdx
0x180013d8e  mov     rdi, rcx
0x180013d91  movups  xmmword ptr [rbp+Src], xmm0
0x180013d95  jnz     short loc_180013DBC
0x180013d97  lea     rcx, [rbp+arg_0]; struct _SOCKET_BROKER_SSL_CONTEXT **
0x180013d9b  call    ?FreeSocketBrokerSslContext@SharedSocket@@CAXPEAPEAU_SOCKET_BROKER_SSL_CONTEXT@@@Z; SharedSocket::FreeSocketBrokerSslContext(_SOCKET_BROKER_SSL_CONTEXT * *)
0x180013da0  mov     rcx, [rbp+Src+8]; pvContextBuffer
0x180013da4  test    rcx, rcx
0x180013da7  jnz     loc_180013EF1
0x180013dad  mov     eax, ebx
0x180013daf  add     rsp, 48h
0x180013db3  pop     r15
0x180013db5  pop     r14
0x180013db7  pop     rdi
0x180013db8  pop     rsi
0x180013db9  pop     rbx
0x180013dba  pop     rbp
0x180013dbb  retn
0x180013dbc  cmp     qword ptr [rcx+98h], 0FFFFFFFFFFFFFFFFh
0x180013dc4  jz      short loc_180013D97
0x180013dc6  cmp     [rcx+88h], rbx
0x180013dcd  jz      short loc_180013D97
0x180013dcf  mov     ecx, 30h ; '0'; dwBytes
0x180013dd4  call    ?MALLOC@@YAPEAX_K@Z; MALLOC(unsigned __int64)
0x180013dd9  mov     [rbp+arg_0], rax
0x180013ddd  mov     rsi, rax
0x180013de0  test    rax, rax
0x180013de3  jnz     short loc_180013E14
0x180013de5  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180013dec  jz      short loc_180013D97
0x180013dee  lea     r8, aSharedsocketGe_1; "SharedSocket:GetSslContext AllocatedSsl"...
0x180013df5  jmp     short loc_180013DFE
0x180013df7  lea     r8, aSharedsocketGe_2; "SharedSocket:GetSslContext Allocating E"...
0x180013dfe  xor     r9d, r9d
0x180013e01  jmp     short loc_180013E0D
0x180013e03  mov     r9d, eax
0x180013e06  lea     r8, aSharedsocketGe; "SharedSocket:GetSslContext ExportSecuri"...
0x180013e0d  call    McTemplateU0zq_EventWriteTransfer
0x180013e12  jmp     short loc_180013D97
0x180013e14  mov     rcx, [rdi+88h]
0x180013e1b  mov     rdx, rsi
0x180013e1e  call    NcbUtilsAllocCopyString
0x180013e23  mov     ebx, eax
0x180013e25  test    eax, eax
0x180013e27  jz      short loc_180013E42
0x180013e29  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180013e30  jz      loc_180013D97
0x180013e36  mov     r9d, eax
0x180013e39  lea     r8, aSharedsocketGe_0; "SharedSocket:GetSslContext copy string "...
0x180013e40  jmp     short loc_180013E0D
0x180013e42  mov     rax, [rdi+0D8h]
0x180013e49  lea     r8, [rbp+Src]
0x180013e4d  xor     r9d, r9d
0x180013e50  xor     edx, edx
0x180013e52  mov     rcx, r14
0x180013e55  mov     rax, [rax+0A0h]
0x180013e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e61  mov     ebx, eax
0x180013e63  test    eax, eax
0x180013e65  jz      short loc_180013E76
0x180013e67  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180013e6e  jz      loc_180013D97
0x180013e74  jmp     short loc_180013E03
0x180013e76  mov     ecx, dword ptr [rbp+Src]; dwBytes
0x180013e79  call    ?MALLOC@@YAPEAX_K@Z; MALLOC(unsigned __int64)
0x180013e7e  mov     [rsi+10h], rax
0x180013e82  test    rax, rax
0x180013e85  jnz     short loc_180013E99
0x180013e87  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180013e8e  jz      loc_180013D97
0x180013e94  jmp     loc_180013DF7
0x180013e99  mov     eax, dword ptr [rbp+Src]
0x180013e9c  mov     [rsi+8], eax
0x180013e9f  mov     eax, dword ptr [rbp+Src+4]
0x180013ea2  mov     [rsi+0Ch], eax
0x180013ea5  xor     eax, eax
0x180013ea7  movups  xmm0, xmmword ptr [rdi+0A0h]
0x180013eae  movups  xmmword ptr [rsi+18h], xmm0
0x180013eb2  movsd   xmm1, qword ptr [rdi+0B0h]
0x180013eba  xorps   xmm0, xmm0
0x180013ebd  movsd   qword ptr [rsi+28h], xmm1
0x180013ec2  mov     r8d, dword ptr [rbp+Src]; Size
0x180013ec6  mov     rdx, [rbp+Src+8]; Src
0x180013eca  movups  xmmword ptr [rdi+0A0h], xmm0
0x180013ed1  mov     [rdi+0B0h], rax
0x180013ed8  mov     rcx, [rsi+10h]; void *
0x180013edc  call    memcpy_0
0x180013ee1  mov     [r15], rsi
0x180013ee4  mov     [rbp+arg_0], 0
0x180013eec  jmp     loc_180013D97
0x180013ef1  call    cs:__imp_FreeContextBuffer
0x180013ef7  jmp     loc_180013DAD
```
