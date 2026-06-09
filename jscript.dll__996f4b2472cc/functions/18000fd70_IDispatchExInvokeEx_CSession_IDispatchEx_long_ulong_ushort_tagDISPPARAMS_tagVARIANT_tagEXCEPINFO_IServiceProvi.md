# IDispatchExInvokeEx(CSession *,IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x18000fd70`
- end: `0x180010109`
- name: `?IDispatchExInvokeEx@@YAJPEAVCSession@@PEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `921`
- prototype: `__int64 __usercall@<rax>(struct CSession *@<rcx>, struct IDispatchEx *@<rdx>, int@<r8d>, unsigned int@<r9d>, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800105a0`

## callees

- `0x18000f108`
- `0x18000f1e0`
- `0x18000fd70`
- `0x180010110`
- `0x1800138a0`
- `0x18001f080`
- `0x18002ead0`
- `0x180051824`
- `0x180051b64`
- `0x180098010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1800100b2`
- `KERNEL32!TlsGetValue` at `0x1800100b2`

## pseudocode

```c
__int64 __fastcall IDispatchExInvokeEx(
        struct CSession *a1,
        struct IDispatch *a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *a7,
        struct tagEXCEPINFO *a8,
        struct IServiceProvider *a9)
{
  char v9; // r15
  __int64 v13; // rax
  char *v14; // rbx
  int v15; // esi
  _QWORD *Value; // rax
  __int64 v17; // rsi
  __int64 v18; // r8
  struct GL *v19; // rcx
  int v20; // eax
  __int64 v21; // r11
  __int64 v22; // r14
  __int64 v24; // rcx
  unsigned int v25; // ebx
  int v26; // r8d
  _QWORD *v27; // rdx
  int v28; // edi
  __int64 *v29; // r10
  __int64 v30; // rax
  int *v31; // r9
  __int64 v32; // r12
  unsigned int *v33; // r15
  int v34; // edx
  __int64 v35; // rax
  int v36; // ecx
  int v37; // eax
  void (__fastcall *v38)(__int64, __int64, __int128 *, _QWORD, int, int, _QWORD); // rax
  __int128 v39; // [rsp+50h] [rbp-48h] BYREF
  __int64 v40; // [rsp+60h] [rbp-38h]

  v9 = 0;
  if ( a1 )
  {
    v13 = *((_QWORD *)a1 + 5);
    if ( v13 )
    {
      if ( *(_QWORD *)(v13 + 936) )
      {
        v9 = CSession::IsResponseDotWrite(a1, a2, a3);
        if ( !v9 )
          CSession::SendRuntimeScriptInfoToHost(a1, SCRIPTTRACEINFO_COMCALLSTART);
      }
    }
  }
  v14 = (char *)a1 + 40;
  if ( (unsigned int)FStackAvailable(*((struct ThreadGlobals **)a1 + 123), 0x10000u) )
  {
    if ( !*(_QWORD *)v14
      || *(_QWORD *)v14 == -216
      || *(_DWORD *)(*(_QWORD *)v14 + 220LL) != 1
      || (v15 = JAmsi::JAmsiProcessor((JAmsi *)(*(_QWORD *)v14 + 216LL), a2, a3, a6, a1), v15 >= 0) )
    {
      Value = (_QWORD *)*((_QWORD *)a1 + 123);
      *(_QWORD *)&v39 = Value;
      if ( Value || (Value = TlsGetValue(g_luTls), (*(_QWORD *)&v39 = Value) != 0) )
      {
        v17 = Value[3];
        v40 = v17;
        *((_QWORD *)&v39 + 1) = 0;
        if ( v17 )
          Value[3] = 0;
        ClearFPUStatus();
      }
      else
      {
        v17 = v40;
      }
      if ( *(_QWORD *)v14 )
      {
        v18 = *(unsigned int *)(*(_QWORD *)v14 + 1008LL);
        if ( *((int *)a1 + 251) < 0 )
        {
          v20 = TrapIDispatchExInvokeEx((struct IDispatchEx *)a2, a3, v18, a5, a6, a7, a8, a9);
        }
        else if ( v17 && (v19 = *(struct GL **)(v17 + 704)) != 0 )
        {
          v20 = CatchIDispatchExInvokeEx(v19, (struct IDispatchEx *)a2, a3, v18, a5, a6, a7, a8, a9);
        }
        else
        {
          v20 = ((__int64 (__fastcall *)(struct IDispatch *, _QWORD, __int64, _QWORD, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *))a2->lpVtbl[1].AddRef)(
                  a2,
                  a3,
                  v18,
                  a5,
                  a6,
                  a7,
                  a8,
                  a9);
        }
        v15 = v20;
        TLS_NoDestructor::Close((TLS_NoDestructor *)&v39);
      }
      else
      {
        TLS_NoDestructor::Close((TLS_NoDestructor *)&v39);
        v15 = -2147418113;
      }
    }
  }
  else
  {
    v15 = -2147024882;
  }
  if ( !v9 )
  {
    v21 = *(_QWORD *)v14;
    if ( *(_QWORD *)v14 )
    {
      v22 = *(_QWORD *)(v21 + 936);
      if ( v22 )
      {
        v24 = *((_QWORD *)a1 + 10);
        v25 = 0;
        if ( v24 )
        {
          v26 = 0;
          v27 = (_QWORD *)(v24 + 56);
          v28 = 0;
          while ( v24 )
          {
            v29 = *(__int64 **)(v24 + 56);
            if ( v29 )
            {
              if ( *v27 )
              {
                v30 = *v29;
                if ( *v29 )
                {
                  v31 = *(int **)(v30 + 64);
                  v32 = *(_QWORD *)(v30 + 72);
                  v33 = (unsigned int *)(v32 + v31[2]);
                  if ( v33 )
                  {
                    if ( v31[3] == 32 )
                    {
                      v34 = *(_DWORD *)(v24 + 168);
                      if ( v34 < 0
                        || (v35 = v29[2], v34 >= *(_DWORD *)(v35 + 28))
                        || (v36 = v34 + *(_DWORD *)(v35 + 24), v36 < 0)
                        || v36 >= v31[10] )
                      {
                        v37 = 0;
                      }
                      else
                      {
                        v26 = *(_QWORD *)(v32 + v31[9] + 8LL * v36);
                        v37 = HIDWORD(*(_QWORD *)(v32 + v31[9] + 8LL * v36));
                      }
                      v25 = *v33;
                      v28 = v37 + v26;
                      break;
                    }
                  }
                }
              }
            }
            v24 = *(_QWORD *)(v24 + 16);
          }
        }
        else
        {
          v28 = 0;
          v26 = 0;
        }
        v38 = *(void (__fastcall **)(__int64, __int64, __int128 *, _QWORD, int, int, _QWORD))(*(_QWORD *)v22 + 24LL);
        v39 = *(_OWORD *)(v21 + 944);
        v38(v22, 3, &v39, v25, v26, v28, 0);
      }
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000fd70  mov     [rsp+arg_8], rbx
0x18000fd75  mov     [rsp+arg_10], rbp
0x18000fd7a  push    rsi
0x18000fd7b  push    rdi
0x18000fd7c  push    r12
0x18000fd7e  push    r14
0x18000fd80  push    r15
0x18000fd82  sub     rsp, 70h
0x18000fd86  xor     r15b, r15b
0x18000fd89  mov     ebp, r8d
0x18000fd8c  mov     r14, rdx
0x18000fd8f  mov     rdi, rcx
0x18000fd92  test    rcx, rcx
0x18000fd95  jz      short loc_18000FDAE
0x18000fd97  mov     rax, [rcx+28h]
0x18000fd9b  test    rax, rax
0x18000fd9e  jz      short loc_18000FDAE
0x18000fda0  cmp     qword ptr [rax+3A8h], 0
0x18000fda8  jnz     loc_1800100D6
0x18000fdae  mov     rcx, [rdi+3D8h]; struct ThreadGlobals *
0x18000fdb5  lea     rbx, [rdi+28h]
0x18000fdb9  mov     edx, 10000h; unsigned int
0x18000fdbe  call    ?FStackAvailable@@YAHPEAVThreadGlobals@@I@Z; FStackAvailable(ThreadGlobals *,uint)
0x18000fdc3  test    eax, eax
0x18000fdc5  jz      loc_18000FF11
0x18000fdcb  mov     rcx, [rbx]
0x18000fdce  mov     r12, [rsp+98h+arg_28]
0x18000fdd6  test    rcx, rcx
0x18000fdd9  jz      short loc_18000FE07
0x18000fddb  add     rcx, 0D8h; this
0x18000fde2  jz      short loc_18000FE07
0x18000fde4  cmp     dword ptr [rcx+4], 1
0x18000fde8  jnz     short loc_18000FE07
0x18000fdea  mov     r9, r12; struct tagDISPPARAMS *
0x18000fded  mov     [rsp+98h+var_78], rdi; struct CSession *
0x18000fdf2  mov     r8d, ebp; int
0x18000fdf5  mov     rdx, r14; struct IDispatch *
0x18000fdf8  call    ?JAmsiProcessor@JAmsi@@QEAAJPEAUIDispatch@@JPEAUtagDISPPARAMS@@PEAVCSession@@@Z; JAmsi::JAmsiProcessor(IDispatch *,long,tagDISPPARAMS *,CSession *)
0x18000fdfd  mov     esi, eax
0x18000fdff  test    eax, eax
0x18000fe01  js      loc_18000FEC7
0x18000fe07  mov     rax, [rdi+3D8h]
0x18000fe0e  mov     qword ptr [rsp+98h+var_48], rax
0x18000fe13  test    rax, rax
0x18000fe16  jz      loc_1800100AC
0x18000fe1c  mov     rsi, [rax+18h]
0x18000fe20  mov     [rsp+98h+var_38], rsi
0x18000fe25  mov     qword ptr [rsp+98h+var_48+8], 0
0x18000fe2e  test    rsi, rsi
0x18000fe31  jz      short loc_18000FE3B
0x18000fe33  mov     qword ptr [rax+18h], 0
0x18000fe3b  call    ?ClearFPUStatus@@YAXXZ; ClearFPUStatus(void)
0x18000fe40  mov     rax, [rbx]
0x18000fe43  test    rax, rax
0x18000fe46  jz      loc_18000FF00
0x18000fe4c  cmp     dword ptr [rdi+3ECh], 0
0x18000fe53  mov     r8d, [rax+3F0h]; unsigned int
0x18000fe5a  jl      loc_18000FF18
0x18000fe60  test    rsi, rsi
0x18000fe63  jz      short loc_18000FE75
0x18000fe65  mov     rcx, [rsi+2C0h]; struct GL *
0x18000fe6c  test    rcx, rcx
0x18000fe6f  jnz     loc_18000FF5C
0x18000fe75  mov     rcx, [rsp+98h+arg_40]
0x18000fe7d  mov     edx, ebp
0x18000fe7f  mov     rax, [r14]
0x18000fe82  movzx   r9d, [rsp+98h+arg_20]
0x18000fe8b  mov     [rsp+98h+var_60], rcx
0x18000fe90  mov     rcx, [rsp+98h+arg_38]
0x18000fe98  mov     rax, [rax+40h]
0x18000fe9c  mov     [rsp+98h+var_68], rcx
0x18000fea1  mov     rcx, [rsp+98h+arg_30]
0x18000fea9  mov     [rsp+98h+var_70], rcx
0x18000feae  mov     rcx, r14
0x18000feb1  mov     [rsp+98h+var_78], r12
0x18000feb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000febb  lea     rcx, [rsp+98h+var_48]; this
0x18000fec0  mov     esi, eax
0x18000fec2  call    ?Close@TLS_NoDestructor@@QEAAXXZ; TLS_NoDestructor::Close(void)
0x18000fec7  test    r15b, r15b
0x18000feca  jnz     short loc_18000FEE4
0x18000fecc  mov     r11, [rbx]
0x18000fecf  test    r11, r11
0x18000fed2  jz      short loc_18000FEE4
0x18000fed4  mov     r14, [r11+3A8h]
0x18000fedb  test    r14, r14
0x18000fede  jnz     loc_18000FFA8
0x18000fee4  lea     r11, [rsp+98h+var_28]
0x18000fee9  mov     eax, esi
0x18000feeb  mov     rbx, [r11+38h]
0x18000feef  mov     rbp, [r11+40h]
0x18000fef3  mov     rsp, r11
0x18000fef6  pop     r15
0x18000fef8  pop     r14
0x18000fefa  pop     r12
0x18000fefc  pop     rdi
0x18000fefd  pop     rsi
0x18000fefe  retn
0x18000ff00  lea     rcx, [rsp+98h+var_48]; this
0x18000ff05  call    ?Close@TLS_NoDestructor@@QEAAXXZ; TLS_NoDestructor::Close(void)
0x18000ff0a  mov     esi, 8000FFFFh
0x18000ff0f  jmp     short loc_18000FEC7
0x18000ff11  mov     esi, 8007000Eh
0x18000ff16  jmp     short loc_18000FEC7
0x18000ff18  mov     rax, [rsp+98h+arg_40]
0x18000ff20  mov     edx, ebp; int
0x18000ff22  movzx   r9d, [rsp+98h+arg_20]; unsigned __int16
0x18000ff2b  mov     rcx, r14; struct IDispatchEx *
0x18000ff2e  mov     [rsp+98h+var_60], rax; struct IServiceProvider *
0x18000ff33  mov     rax, [rsp+98h+arg_38]
0x18000ff3b  mov     [rsp+98h+var_68], rax; struct tagEXCEPINFO *
0x18000ff40  mov     rax, [rsp+98h+arg_30]
0x18000ff48  mov     [rsp+98h+var_70], rax; struct tagVARIANT *
0x18000ff4d  mov     [rsp+98h+var_78], r12; struct tagDISPPARAMS *
0x18000ff52  call    ?TrapIDispatchExInvokeEx@@YAJPEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z; TrapIDispatchExInvokeEx(IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)
0x18000ff57  jmp     loc_18000FEBB
0x18000ff5c  mov     rax, [rsp+98h+arg_40]
0x18000ff64  mov     r9d, r8d; unsigned int
0x18000ff67  mov     [rsp+98h+var_58], rax; struct IServiceProvider *
0x18000ff6c  mov     r8d, ebp; int
0x18000ff6f  mov     rax, [rsp+98h+arg_38]
0x18000ff77  mov     rdx, r14; struct IDispatchEx *
0x18000ff7a  mov     [rsp+98h+var_60], rax; struct tagEXCEPINFO *
0x18000ff7f  mov     rax, [rsp+98h+arg_30]
0x18000ff87  mov     [rsp+98h+var_68], rax; struct tagVARIANT *
0x18000ff8c  movzx   eax, [rsp+98h+arg_20]
0x18000ff94  mov     [rsp+98h+var_70], r12; struct tagDISPPARAMS *
0x18000ff99  mov     word ptr [rsp+98h+var_78], ax; unsigned __int16
0x18000ff9e  call    ?CatchIDispatchExInvokeEx@@YAJPEAVGL@@PEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z; CatchIDispatchExInvokeEx(GL *,IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)
0x18000ffa3  jmp     loc_18000FEBB
0x18000ffa8  mov     rcx, [rdi+50h]
0x18000ffac  xor     ebx, ebx
0x18000ffae  test    rcx, rcx
0x18000ffb1  jz      loc_1800100FF
0x18000ffb7  xor     r8d, r8d
0x18000ffba  lea     rdx, [rcx+38h]
0x18000ffbe  xor     edi, edi
0x18000ffc0  test    rcx, rcx
0x18000ffc3  jz      loc_180010062
0x18000ffc9  mov     r10, [rcx+38h]
0x18000ffcd  test    r10, r10
0x18000ffd0  jz      loc_1800100A3
0x18000ffd6  cmp     [rdx], rbx
0x18000ffd9  jz      loc_1800100A3
0x18000ffdf  mov     rax, [r10]
0x18000ffe2  test    rax, rax
0x18000ffe5  jz      loc_1800100A3
0x18000ffeb  mov     r9, [rax+40h]
0x18000ffef  mov     r12, [rax+48h]
0x18000fff3  movsxd  r15, dword ptr [r9+8]
0x18000fff7  add     r15, r12
0x18000fffa  jz      loc_1800100A3
0x180010000  cmp     dword ptr [r9+0Ch], 20h ; ' '
0x180010005  jnz     loc_1800100A3
0x18001000b  mov     edx, [rcx+0A8h]
0x180010011  test    edx, edx
0x180010013  js      loc_1800100F8
0x180010019  mov     rax, [r10+10h]
0x18001001d  cmp     edx, [rax+1Ch]
0x180010020  jge     loc_1800100F8
0x180010026  mov     ecx, [rax+18h]
0x180010029  add     ecx, edx
0x18001002b  js      loc_1800100F8
0x180010031  cmp     ecx, [r9+28h]
0x180010035  jge     loc_1800100F8
0x18001003b  movsxd  rax, dword ptr [r9+24h]
0x18001003f  add     rax, r12
0x180010042  movsxd  rcx, ecx
0x180010045  mov     rcx, [rax+rcx*8]
0x180010049  mov     [rsp+98h+arg_0], rcx
0x180010051  mov     r8d, ecx
0x180010054  mov     eax, dword ptr [rsp+98h+arg_0+4]
0x18001005b  mov     ebx, [r15]
0x18001005e  lea     edi, [rax+r8]
0x180010062  mov     rdx, [r14]
0x180010065  mov     r9d, ebx
0x180010068  movups  xmm0, xmmword ptr [r11+3B0h]
0x180010070  mov     [rsp+98h+var_68], 0
0x180010079  mov     rcx, r14
0x18001007c  mov     dword ptr [rsp+98h+var_70], edi
0x180010080  mov     rax, [rdx+18h]
0x180010084  mov     edx, 3
0x180010089  mov     dword ptr [rsp+98h+var_78], r8d
0x18001008e  lea     r8, [rsp+98h+var_48]
0x180010093  movdqu  [rsp+98h+var_48], xmm0
0x180010099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001009e  jmp     loc_18000FEE4
0x1800100a3  mov     rcx, [rcx+10h]
0x1800100a7  jmp     loc_18000FFC0
0x1800100ac  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800100b2  call    cs:__imp_TlsGetValue
0x1800100b9  nop     dword ptr [rax+rax+00h]
0x1800100be  mov     qword ptr [rsp+98h+var_48], rax
0x1800100c3  test    rax, rax
0x1800100c6  jnz     loc_18000FE1C
0x1800100cc  mov     rsi, [rsp+98h+var_38]
0x1800100d1  jmp     loc_18000FE40
0x1800100d6  call    ?IsResponseDotWrite@CSession@@QEAA_NPEAUIDispatch@@J@Z; CSession::IsResponseDotWrite(IDispatch *,long)
0x1800100db  mov     r15b, al
0x1800100de  test    al, al
0x1800100e0  jnz     loc_18000FDAE
0x1800100e6  mov     edx, 2; enum tagSCRIPTTRACEINFO
0x1800100eb  mov     rcx, rdi; this
0x1800100ee  call    ?SendRuntimeScriptInfoToHost@CSession@@QEAAJW4tagSCRIPTTRACEINFO@@@Z; CSession::SendRuntimeScriptInfoToHost(tagSCRIPTTRACEINFO)
0x1800100f3  jmp     loc_18000FDAE
0x1800100f8  xor     eax, eax
0x1800100fa  jmp     loc_18001005B
0x1800100ff  xor     edi, edi
0x180010101  xor     r8d, r8d
0x180010104  jmp     loc_180010062
```
