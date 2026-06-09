# MULTI_IPM::InstantiatePipe(_SECURITY_ATTRIBUTES *)

- ea: `0x180029730`
- end: `0x1800299c0`
- name: `?InstantiatePipe@MULTI_IPM@@AEAAJPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `656`
- prototype: `int(MULTI_IPM *__hidden this, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180029690`
- `0x180029b10`

## callees

- `0x180005110`
- `0x180007300`
- `0x1800081e0`
- `0x1800183f8`
- `0x180027520`
- `0x180027bb0`
- `0x18002963c`
- `0x180029730`
- `0x18002d010`

## string_xrefs

- `0x180029786`: `servercommon\inetsrv\iis\iisrearc\core\common\util\multi_ipm.cxx`
- `0x18002989a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\multi_ipm.cxx`
- `0x18002992f`: `servercommon\inetsrv\iis\iisrearc\core\common\util\multi_ipm.cxx`
- `0x18002998b`: `servercommon\inetsrv\iis\iisrearc\core\common\util\multi_ipm.cxx`
- `0x180029864`: `IPM2_MESSAGE_PIPE::InstantiatePipe CreateIpmMessagePipe FAILED hr=0x%08x \n `

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
0x180029730  mov     rax, rsp
0x180029733  mov     [rax+10h], rbx
0x180029737  mov     [rax+20h], rbp
0x18002973b  push    rsi
0x18002973c  push    rdi
0x18002973d  push    r13
0x18002973f  push    r14
0x180029741  push    r15
0x180029743  sub     rsp, 40h
0x180029747  cmp     dword ptr [rcx+40h], 0
0x18002974b  lea     r13, aMultiIpmInstan; "MULTI_IPM::InstantiatePipe"
0x180029752  mov     r14, rdx
0x180029755  mov     qword ptr [rax+18h], 0
0x18002975d  mov     rbp, rcx
0x180029760  mov     dword ptr [rax+8], 0
0x180029767  jz      short loc_180029773
0x180029769  mov     ebx, 1
0x18002976e  jmp     loc_180029970
0x180029773  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002977a  lea     rbx, [rcx+3Ch]
0x18002977e  lea     rsi, [rcx+4Ch]
0x180029782  jz      short loc_1800297B8
0x180029784  mov     eax, [rbx]
0x180029786  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002978d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029794  mov     r9, r13; char *
0x180029797  mov     dword ptr [rsp+68h+var_38], eax
0x18002979b  mov     r8d, 97h; unsigned int
0x1800297a1  mov     eax, [rsi]
0x1800297a3  mov     dword ptr [rsp+68h+var_40], eax; char
0x1800297a7  lea     rax, aInstatiatingNe_0; "Instatiating new pipe. _dwNumPipeInstan"...
0x1800297ae  mov     [rsp+68h+var_48], rax; char *
0x1800297b3  call    PuDbgPrint
0x1800297b8  mov     eax, [rbx]
0x1800297ba  cmp     eax, 0FFh
0x1800297bf  jz      short loc_1800297C5
0x1800297c1  cmp     [rsi], eax
0x1800297c3  jnb     short loc_180029769
0x1800297c5  mov     ecx, 28h ; '('; Size
0x1800297ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800297cf  mov     rdi, rax
0x1800297d2  test    rax, rax
0x1800297d5  jz      loc_18002996B
0x1800297db  lea     rax, ??_7IPM_INSTANCE@@6B@; const IPM_INSTANCE::`vftable'
0x1800297e2  mov     [rdi+8], rbp
0x1800297e6  lea     r15, [rbp+44h]
0x1800297ea  mov     [rdi], rax
0x1800297ed  mov     rcx, r15; this
0x1800297f0  mov     qword ptr [rdi+10h], 0
0x1800297f8  mov     qword ptr [rdi+18h], 0
0x180029800  mov     qword ptr [rdi+20h], 0
0x180029808  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18002980d  mov     rdx, [rbp+20h]; unsigned __int16 *
0x180029811  lea     rax, [rsp+68h+arg_0]
0x180029816  mov     [rsp+68h+var_30], rax; int *
0x18002981b  xor     r9d, r9d
0x18002981e  cmp     [rsi], r9d
0x180029821  lea     rax, [rsp+68h+arg_10]
0x180029829  mov     [rsp+68h+var_38], rax; struct IPM2_MESSAGE_PIPE **
0x18002982e  mov     r8d, 1; int
0x180029834  mov     eax, [rbx]
0x180029836  setz    r9b; int
0x18002983a  mov     [rsp+68h+var_40], r14; struct _SECURITY_ATTRIBUTES *
0x18002983f  mov     rcx, rdi; struct IPM2_MESSAGE_ACCEPTOR *
0x180029842  mov     dword ptr [rsp+68h+var_48], eax; unsigned int
0x180029846  call    ?CreateIpmMessagePipe@IPM2_MESSAGE_PIPE@@SAJPEAVIPM2_MESSAGE_ACCEPTOR@@PEBGHHKPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@PEAH@Z; IPM2_MESSAGE_PIPE::CreateIpmMessagePipe(IPM2_MESSAGE_ACCEPTOR *,ushort const *,int,int,ulong,_SECURITY_ATTRIBUTES *,IPM2_MESSAGE_PIPE * *,int *)
0x18002984b  mov     ebx, eax
0x18002984d  test    eax, eax
0x18002984f  jns     short loc_18002986D
0x180029851  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180029858  jz      short loc_1800298AE
0x18002985a  mov     dword ptr [rsp+68h+var_40], eax
0x18002985e  mov     r8d, 0B8h
0x180029864  lea     rax, aIpm2MessagePip_33; "IPM2_MESSAGE_PIPE::InstantiatePipe Crea"...
0x18002986b  jmp     short loc_180029893
0x18002986d  cmp     qword ptr [rdi+10h], 0
0x180029872  jz      short loc_1800298C3
0x180029874  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002987b  mov     ebx, 8000FFFFh
0x180029880  jz      short loc_1800298AE
0x180029882  mov     dword ptr [rsp+68h+var_40], ebx; char
0x180029886  lea     rax, aIpm2MessagePip_39; "IPM2_MESSAGE_PIPE::InstantiatePipe SetI"...
0x18002988d  mov     r8d, 0C1h; unsigned int
0x180029893  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002989a  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800298a1  mov     r9, r13; char *
0x1800298a4  mov     [rsp+68h+var_48], rax; char *
0x1800298a9  call    PuDbgPrint
0x1800298ae  mov     rcx, r15; this
0x1800298b1  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800298b6  mov     r14, [rsp+68h+arg_10]
0x1800298be  jmp     loc_180029954
0x1800298c3  mov     rax, [rsp+68h+arg_10]
0x1800298cb  add     rbp, 50h ; 'P'
0x1800298cf  mov     [rdi+10h], rax
0x1800298d3  xor     r14d, r14d
0x1800298d6  mov     rdx, [rbp+8]
0x1800298da  cmp     [rdx], rbp
0x1800298dd  jz      short loc_1800298E5
0x1800298df  lea     ecx, [r14+3]
0x1800298e3  int     29h; Win8: RtlFailFast(ecx)
0x1800298e5  lea     rax, [rdi+18h]
0x1800298e9  xor     ebx, ebx
0x1800298eb  mov     [rax], rbp
0x1800298ee  mov     [rax+8], rdx
0x1800298f2  mov     [rdx], rax
0x1800298f5  mov     [rbp+8], rax
0x1800298f9  lock inc dword ptr [rsi]
0x1800298fc  mov     rcx, r15; this
0x1800298ff  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180029904  cmp     [rsp+68h+arg_0], ebx
0x180029908  jz      short loc_180029970
0x18002990a  mov     rax, [rdi]
0x18002990d  mov     rcx, rdi
0x180029910  mov     rax, [rax+8]
0x180029914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029919  mov     ebx, eax
0x18002991b  test    eax, eax
0x18002991d  jns     short loc_180029970
0x18002991f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180029926  jz      short loc_180029954
0x180029928  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002992f  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029936  mov     dword ptr [rsp+68h+var_40], eax; char
0x18002993a  mov     r9, r13; char *
0x18002993d  lea     rax, aIpm2MessagePip_3; "IPM2_MESSAGE_PIPE::InstantiatePipe Pipe"...
0x180029944  mov     r8d, 0D7h; unsigned int
0x18002994a  mov     [rsp+68h+var_48], rax; char *
0x18002994f  call    PuDbgPrint
0x180029954  mov     rcx, rdi; this
0x180029957  call    ??_GIPM_INSTANCE@@QEAAPEAXI@Z; IPM_INSTANCE::`scalar deleting destructor'(uint)
0x18002995c  test    r14, r14
0x18002995f  jz      short loc_180029970
0x180029961  mov     rcx, r14; this
0x180029964  call    ?DestroyIpmMessagePipe@IPM2_MESSAGE_PIPE@@QEAAXXZ; IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe(void)
0x180029969  jmp     short loc_180029970
0x18002996b  mov     ebx, 8007000Eh
0x180029970  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180029977  jz      short loc_1800299A5
0x180029979  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029980  lea     rax, aInstatiatingNe; "Instatiating new pipe result hr=0x%08X"...
0x180029987  mov     dword ptr [rsp+68h+var_40], ebx; char
0x18002998b  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029992  mov     r9, r13; char *
0x180029995  mov     [rsp+68h+var_48], rax; char *
0x18002999a  mov     r8d, 0F3h; unsigned int
0x1800299a0  call    PuDbgPrint
0x1800299a5  lea     r11, [rsp+68h+var_28]
0x1800299aa  mov     eax, ebx
0x1800299ac  mov     rbx, [r11+38h]
0x1800299b0  mov     rbp, [r11+48h]
0x1800299b4  mov     rsp, r11
0x1800299b7  pop     r15
0x1800299b9  pop     r14
0x1800299bb  pop     r13
0x1800299bd  pop     rdi
0x1800299be  pop     rsi
0x1800299bf  retn
```
