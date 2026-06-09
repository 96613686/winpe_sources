# MULTI_IPM::InstantiatePipe(_SECURITY_ATTRIBUTES *)

- ea: `0x18002b570`
- end: `0x18002b801`
- name: `?InstantiatePipe@MULTI_IPM@@AEAAJPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `657`
- prototype: `__int64 __fastcall(MULTI_IPM *this, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002b4d0`
- `0x18002b960`

## callees

- `0x180005c80`
- `0x180008000`
- `0x180008f20`
- `0x180019230`
- `0x1800291f0`
- `0x1800298e0`
- `0x18002b47c`
- `0x18002b570`
- `0x18002f010`

## string_xrefs

- `0x18002b5c6`: `servercommon\inetsrv\iis\iisrearc\core\common\util\multi_ipm.cxx`
- `0x18002b6da`: `servercommon\inetsrv\iis\iisrearc\core\common\util\multi_ipm.cxx`
- `0x18002b76f`: `servercommon\inetsrv\iis\iisrearc\core\common\util\multi_ipm.cxx`
- `0x18002b7cb`: `servercommon\inetsrv\iis\iisrearc\core\common\util\multi_ipm.cxx`
- `0x18002b6a4`: `IPM2_MESSAGE_PIPE::InstantiatePipe CreateIpmMessagePipe FAILED hr=0x%08x \n `

## pseudocode

```c
__int64 __fastcall MULTI_IPM::InstantiatePipe(MULTI_IPM *this, struct _SECURITY_ATTRIBUTES *a2)
{
  bool v2; // zf
  unsigned int v5; // ebx
  DWORD *v6; // rbx
  volatile signed __int32 *v7; // rsi
  _QWORD *v8; // rdi
  CReaderWriterLock3 *v9; // r15
  int v10; // eax
  unsigned int v11; // edx
  IPM2_MESSAGE_PIPE *v12; // r14
  char *v13; // rbp
  char **v14; // rdx
  int v15; // eax
  int v17; // [rsp+70h] [rbp+8h] BYREF
  struct IPM2_MESSAGE_PIPE *v18; // [rsp+80h] [rbp+18h] BYREF

  v2 = *((_DWORD *)this + 16) == 0;
  v18 = 0;
  v17 = 0;
  if ( !v2 )
    goto LABEL_2;
  v6 = (DWORD *)((char *)this + 60);
  v7 = (volatile signed __int32 *)((char *)this + 76);
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\multi_ipm.cxx",
      0x97u,
      "MULTI_IPM::InstantiatePipe",
      "Instatiating new pipe. _dwNumPipeInstances: %d, _dwMaxPipeInstances: %d\n",
      *v7);
  if ( *v6 != 255 && *v7 >= *v6 )
  {
LABEL_2:
    v5 = 1;
    goto LABEL_24;
  }
  v8 = operator new(0x28u);
  if ( !v8 )
  {
    v5 = -2147024882;
    goto LABEL_24;
  }
  v8[1] = this;
  v9 = (MULTI_IPM *)((char *)this + 68);
  *v8 = &IPM_INSTANCE::`vftable';
  v8[2] = 0;
  v8[3] = 0;
  v8[4] = 0;
  CReaderWriterLock3::WriteLock((MULTI_IPM *)((char *)this + 68));
  v10 = IPM2_MESSAGE_PIPE::CreateIpmMessagePipe(
          (struct IPM2_MESSAGE_ACCEPTOR *)v8,
          *((const unsigned __int16 **)this + 4),
          1,
          *v7 == 0,
          *v6,
          a2,
          &v18,
          &v17);
  v5 = v10;
  if ( v10 < 0 )
  {
    if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\multi_ipm.cxx",
        0xB8u,
        "MULTI_IPM::InstantiatePipe",
        "IPM2_MESSAGE_PIPE::InstantiatePipe CreateIpmMessagePipe FAILED hr=0x%08x \n ",
        v10);
LABEL_14:
    CReaderWriterLock3::WriteUnlock((MULTI_IPM *)((char *)this + 68));
    v12 = v18;
LABEL_21:
    IPM_INSTANCE::`scalar deleting destructor'((IPM_INSTANCE *)v8, v11);
    if ( v12 )
      IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe(v12);
    goto LABEL_24;
  }
  if ( v8[2] )
  {
    v5 = -2147418113;
    if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\multi_ipm.cxx",
        0xC1u,
        "MULTI_IPM::InstantiatePipe",
        "IPM2_MESSAGE_PIPE::InstantiatePipe SetIpmPipe FAILED hr=0x%08x \n ",
        255);
    goto LABEL_14;
  }
  v13 = (char *)this + 80;
  v8[2] = v18;
  v12 = 0;
  v14 = (char **)*((_QWORD *)v13 + 1);
  if ( *v14 != v13 )
    __fastfail(3u);
  v5 = 0;
  v8[3] = v13;
  v8[4] = v14;
  *v14 = (char *)(v8 + 3);
  *((_QWORD *)v13 + 1) = v8 + 3;
  _InterlockedIncrement(v7);
  CReaderWriterLock3::WriteUnlock(v9);
  if ( v17 )
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
    v5 = v15;
    if ( v15 < 0 )
    {
      if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\multi_ipm.cxx",
          0xD7u,
          "MULTI_IPM::InstantiatePipe",
          "IPM2_MESSAGE_PIPE::InstantiatePipe PipeConnected FAILED hr=0x%08x \n ",
          v15);
      goto LABEL_21;
    }
  }
LABEL_24:
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\multi_ipm.cxx",
      0xF3u,
      "MULTI_IPM::InstantiatePipe",
      "Instatiating new pipe result hr=0x%08X\n",
      v5);
  return v5;
}

```

## disassembly

```asm
0x18002b570  mov     rax, rsp
0x18002b573  mov     [rax+10h], rbx
0x18002b577  mov     [rax+20h], rbp
0x18002b57b  push    rsi
0x18002b57c  push    rdi
0x18002b57d  push    r13
0x18002b57f  push    r14
0x18002b581  push    r15
0x18002b583  sub     rsp, 40h
0x18002b587  cmp     dword ptr [rcx+40h], 0
0x18002b58b  lea     r13, aMultiIpmInstan; "MULTI_IPM::InstantiatePipe"
0x18002b592  mov     r14, rdx
0x18002b595  mov     qword ptr [rax+18h], 0
0x18002b59d  mov     rbp, rcx
0x18002b5a0  mov     dword ptr [rax+8], 0
0x18002b5a7  jz      short loc_18002B5B3
0x18002b5a9  mov     ebx, 1
0x18002b5ae  jmp     loc_18002B7B0
0x18002b5b3  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002b5ba  lea     rbx, [rcx+3Ch]
0x18002b5be  lea     rsi, [rcx+4Ch]
0x18002b5c2  jz      short loc_18002B5F8
0x18002b5c4  mov     eax, [rbx]
0x18002b5c6  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b5cd  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002b5d4  mov     r9, r13; char *
0x18002b5d7  mov     dword ptr [rsp+68h+var_38], eax
0x18002b5db  mov     r8d, 97h; unsigned int
0x18002b5e1  mov     eax, [rsi]
0x18002b5e3  mov     dword ptr [rsp+68h+var_40], eax; char
0x18002b5e7  lea     rax, aInstatiatingNe_0; "Instatiating new pipe. _dwNumPipeInstan"...
0x18002b5ee  mov     [rsp+68h+var_48], rax; char *
0x18002b5f3  call    PuDbgPrint
0x18002b5f8  mov     eax, [rbx]
0x18002b5fa  cmp     eax, 0FFh
0x18002b5ff  jz      short loc_18002B605
0x18002b601  cmp     [rsi], eax
0x18002b603  jnb     short loc_18002B5A9
0x18002b605  mov     ecx, 28h ; '('; Size
0x18002b60a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b60f  mov     rdi, rax
0x18002b612  test    rax, rax
0x18002b615  jz      loc_18002B7AB
0x18002b61b  lea     rax, ??_7IPM_INSTANCE@@6B@; const IPM_INSTANCE::`vftable'
0x18002b622  mov     [rdi+8], rbp
0x18002b626  lea     r15, [rbp+44h]
0x18002b62a  mov     [rdi], rax
0x18002b62d  mov     rcx, r15; this
0x18002b630  mov     qword ptr [rdi+10h], 0
0x18002b638  mov     qword ptr [rdi+18h], 0
0x18002b640  mov     qword ptr [rdi+20h], 0
0x18002b648  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18002b64d  mov     rdx, [rbp+20h]; unsigned __int16 *
0x18002b651  lea     rax, [rsp+68h+arg_0]
0x18002b656  mov     [rsp+68h+var_30], rax; int *
0x18002b65b  xor     r9d, r9d
0x18002b65e  cmp     [rsi], r9d
0x18002b661  lea     rax, [rsp+68h+arg_10]
0x18002b669  mov     [rsp+68h+var_38], rax; struct IPM2_MESSAGE_PIPE **
0x18002b66e  mov     r8d, 1; int
0x18002b674  mov     eax, [rbx]
0x18002b676  setz    r9b; int
0x18002b67a  mov     [rsp+68h+var_40], r14; struct _SECURITY_ATTRIBUTES *
0x18002b67f  mov     rcx, rdi; struct IPM2_MESSAGE_ACCEPTOR *
0x18002b682  mov     dword ptr [rsp+68h+var_48], eax; unsigned int
0x18002b686  call    ?CreateIpmMessagePipe@IPM2_MESSAGE_PIPE@@SAJPEAVIPM2_MESSAGE_ACCEPTOR@@PEBGHHKPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@PEAH@Z; IPM2_MESSAGE_PIPE::CreateIpmMessagePipe(IPM2_MESSAGE_ACCEPTOR *,ushort const *,int,int,ulong,_SECURITY_ATTRIBUTES *,IPM2_MESSAGE_PIPE * *,int *)
0x18002b68b  mov     ebx, eax
0x18002b68d  test    eax, eax
0x18002b68f  jns     short loc_18002B6AD
0x18002b691  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002b698  jz      short loc_18002B6EE
0x18002b69a  mov     dword ptr [rsp+68h+var_40], eax
0x18002b69e  mov     r8d, 0B8h
0x18002b6a4  lea     rax, aIpm2MessagePip_33; "IPM2_MESSAGE_PIPE::InstantiatePipe Crea"...
0x18002b6ab  jmp     short loc_18002B6D3
0x18002b6ad  cmp     qword ptr [rdi+10h], 0
0x18002b6b2  jz      short loc_18002B703
0x18002b6b4  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002b6bb  mov     ebx, 8000FFFFh
0x18002b6c0  jz      short loc_18002B6EE
0x18002b6c2  mov     dword ptr [rsp+68h+var_40], ebx; char
0x18002b6c6  lea     rax, aIpm2MessagePip_39; "IPM2_MESSAGE_PIPE::InstantiatePipe SetI"...
0x18002b6cd  mov     r8d, 0C1h; unsigned int
0x18002b6d3  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002b6da  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b6e1  mov     r9, r13; char *
0x18002b6e4  mov     [rsp+68h+var_48], rax; char *
0x18002b6e9  call    PuDbgPrint
0x18002b6ee  mov     rcx, r15; this
0x18002b6f1  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18002b6f6  mov     r14, [rsp+68h+arg_10]
0x18002b6fe  jmp     loc_18002B794
0x18002b703  mov     rax, [rsp+68h+arg_10]
0x18002b70b  add     rbp, 50h ; 'P'
0x18002b70f  mov     [rdi+10h], rax
0x18002b713  xor     r14d, r14d
0x18002b716  mov     rdx, [rbp+8]
0x18002b71a  cmp     [rdx], rbp
0x18002b71d  jz      short loc_18002B725
0x18002b71f  lea     ecx, [r14+3]
0x18002b723  int     29h; Win8: RtlFailFast(ecx)
0x18002b725  lea     rax, [rdi+18h]
0x18002b729  xor     ebx, ebx
0x18002b72b  mov     [rax], rbp
0x18002b72e  mov     [rax+8], rdx
0x18002b732  mov     [rdx], rax
0x18002b735  mov     [rbp+8], rax
0x18002b739  lock inc dword ptr [rsi]
0x18002b73c  mov     rcx, r15; this
0x18002b73f  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18002b744  cmp     [rsp+68h+arg_0], ebx
0x18002b748  jz      short loc_18002B7B0
0x18002b74a  mov     rax, [rdi]
0x18002b74d  mov     rcx, rdi
0x18002b750  mov     rax, [rax+8]
0x18002b754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b759  mov     ebx, eax
0x18002b75b  test    eax, eax
0x18002b75d  jns     short loc_18002B7B0
0x18002b75f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002b766  jz      short loc_18002B794
0x18002b768  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002b76f  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b776  mov     dword ptr [rsp+68h+var_40], eax; char
0x18002b77a  mov     r9, r13; char *
0x18002b77d  lea     rax, aIpm2MessagePip_3; "IPM2_MESSAGE_PIPE::InstantiatePipe Pipe"...
0x18002b784  mov     r8d, 0D7h; unsigned int
0x18002b78a  mov     [rsp+68h+var_48], rax; char *
0x18002b78f  call    PuDbgPrint
0x18002b794  mov     rcx, rdi; this
0x18002b797  call    ??_GIPM_INSTANCE@@QEAAPEAXI@Z; IPM_INSTANCE::`scalar deleting destructor'(uint)
0x18002b79c  test    r14, r14
0x18002b79f  jz      short loc_18002B7B0
0x18002b7a1  mov     rcx, r14; this
0x18002b7a4  call    ?DestroyIpmMessagePipe@IPM2_MESSAGE_PIPE@@QEAAXXZ; IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe(void)
0x18002b7a9  jmp     short loc_18002B7B0
0x18002b7ab  mov     ebx, 8007000Eh
0x18002b7b0  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002b7b7  jz      short loc_18002B7E5
0x18002b7b9  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002b7c0  lea     rax, aInstatiatingNe; "Instatiating new pipe result hr=0x%08X"...
0x18002b7c7  mov     dword ptr [rsp+68h+var_40], ebx; char
0x18002b7cb  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b7d2  mov     r9, r13; char *
0x18002b7d5  mov     [rsp+68h+var_48], rax; char *
0x18002b7da  mov     r8d, 0F3h; unsigned int
0x18002b7e0  call    PuDbgPrint
0x18002b7e5  lea     r11, [rsp+68h+var_28]
0x18002b7ea  mov     eax, ebx
0x18002b7ec  mov     rbx, [r11+38h]
0x18002b7f0  mov     rbp, [r11+48h]
0x18002b7f4  mov     rsp, r11
0x18002b7f7  pop     r15
0x18002b7f9  pop     r14
0x18002b7fb  pop     r13
0x18002b7fd  pop     rdi
0x18002b7fe  pop     rsi
0x18002b7ff  retn
```
