# IDispatchExInvokeEx(CSession *,IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x180012ae4`
- end: `0x180012ee2`
- name: `?IDispatchExInvokeEx@@YAJPEAVCSession@@PEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `1022`
- prototype: `__int64 __usercall@<rax>(struct CSession *@<rcx>, struct IDispatchEx *@<rdx>, int@<r8d>, unsigned int@<r9d>, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180013350`

## callees

- `0x180011ecc`
- `0x180011f90`
- `0x180012ae4`
- `0x180012ee8`
- `0x180019b34`
- `0x180019ce0`
- `0x180022010`
- `0x180033640`
- `0x18003d33c`
- `0x180050a38`
- `0x180050dfc`
- `0x180096010`

## import_xrefs

- `msvcrt!_statusfp` at `0x180012c50`
- `msvcrt!_statusfp` at `0x180012c50`
- `msvcrt!_clearfp` at `0x180012ca7`
- `msvcrt!_clearfp` at `0x180012ca7`
- `msvcrt!_controlfp` at `0x180012c64`
- `msvcrt!_controlfp` at `0x180012c64`
- `KERNEL32!TlsGetValue` at `0x180012e85`
- `KERNEL32!TlsGetValue` at `0x180012e85`

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
  __int64 v12; // rax
  char *v13; // rbx
  int v14; // r15d
  __int64 v15; // rdi
  struct GL **v16; // rbp
  COleScript *v17; // r14
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
  unsigned int *v33; // rsi
  int v34; // edx
  __int64 v35; // rax
  int v36; // ecx
  int v37; // eax
  void (__fastcall *v38)(__int64, __int64, __int128 *, _QWORD, int, int, _QWORD); // rax
  __int128 v39; // [rsp+50h] [rbp-58h] BYREF
  struct GL **v40; // [rsp+60h] [rbp-48h]
  char v41; // [rsp+C8h] [rbp+20h]

  v41 = 0;
  if ( a1 )
  {
    v12 = *((_QWORD *)a1 + 5);
    if ( v12 )
    {
      if ( *(_QWORD *)(v12 + 936) )
      {
        v41 = CSession::IsResponseDotWrite(a1, a2, a3);
        if ( !v41 )
          CSession::SendRuntimeScriptInfoToHost(a1, SCRIPTTRACEINFO_COMCALLSTART);
      }
    }
  }
  v13 = (char *)a1 + 40;
  if ( (unsigned int)FStackAvailable(*((struct ThreadGlobals **)a1 + 123), 0x10000u) )
  {
    if ( !*(_QWORD *)v13
      || *(_QWORD *)v13 == -216
      || *(_DWORD *)(*(_QWORD *)v13 + 220LL) != 1
      || (v14 = JAmsi::JAmsiProcessor((JAmsi *)(*(_QWORD *)v13 + 216LL), a2, a3, a6, a1), v14 >= 0) )
    {
      v15 = *((_QWORD *)a1 + 123);
      *(_QWORD *)&v39 = v15;
      if ( v15 || (*(_QWORD *)&v39 = TlsGetValue(g_luTls), (v15 = v39) != 0) )
      {
        v16 = *(struct GL ***)(v15 + 24);
        v17 = 0;
        v40 = v16;
        *((_QWORD *)&v39 + 1) = 0;
        if ( v16 )
          *(_QWORD *)(v15 + 24) = 0;
        ClearFPUStatus();
      }
      else
      {
        v16 = v40;
        v17 = (COleScript *)*((_QWORD *)&v39 + 1);
      }
      if ( *(_QWORD *)v13 )
      {
        v18 = *(unsigned int *)(*(_QWORD *)v13 + 1008LL);
        if ( *((int *)a1 + 251) < 0 )
        {
          v20 = TrapIDispatchExInvokeEx((struct IDispatchEx *)a2, a3, v18, a5, a6, a7, a8, a9);
        }
        else if ( v16 && (v19 = v16[88]) != 0 )
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
        v14 = v20;
        if ( v15 )
        {
          if ( v16 != (struct GL **)v17 && v17 )
          {
            COleScript::OnLeaveScript(v17);
            COleScript::Release(v17);
          }
          *(_QWORD *)(v15 + 24) = v16;
          if ( _statusfp() )
            _clearfp();
          _controlfp(0x1Fu, 0x30F031Fu);
        }
      }
      else
      {
        TLS_NoDestructor::Close((TLS_NoDestructor *)&v39);
        v14 = -2147418113;
      }
    }
  }
  else
  {
    v14 = -2147024882;
  }
  if ( !v41 )
  {
    v21 = *(_QWORD *)v13;
    if ( *(_QWORD *)v13 )
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
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180012ae4  mov     [rsp+arg_8], rbx
0x180012ae9  mov     [rsp+arg_18], r9d
0x180012aee  push    rbp
0x180012aef  push    rsi
0x180012af0  push    rdi
0x180012af1  push    r12
0x180012af3  push    r13
0x180012af5  push    r14
0x180012af7  push    r15
0x180012af9  sub     rsp, 70h
0x180012afd  mov     byte ptr [rsp+0A8h+arg_18], 0
0x180012b05  mov     r13d, r8d
0x180012b08  mov     r12, rdx
0x180012b0b  mov     rsi, rcx
0x180012b0e  test    rcx, rcx
0x180012b11  jz      short loc_180012B2A
0x180012b13  mov     rax, [rcx+28h]
0x180012b17  test    rax, rax
0x180012b1a  jz      short loc_180012B2A
0x180012b1c  cmp     qword ptr [rax+3A8h], 0
0x180012b24  jnz     loc_180012EAB
0x180012b2a  mov     rcx, [rsi+3D8h]; struct ThreadGlobals *
0x180012b31  lea     rbx, [rsi+28h]
0x180012b35  mov     edx, 10000h; unsigned int
0x180012b3a  call    ?FStackAvailable@@YAHPEAVThreadGlobals@@I@Z; FStackAvailable(ThreadGlobals *,uint)
0x180012b3f  test    eax, eax
0x180012b41  jz      loc_180012CD3
0x180012b47  mov     rcx, [rbx]
0x180012b4a  test    rcx, rcx
0x180012b4d  jz      short loc_180012B81
0x180012b4f  add     rcx, 0D8h; this
0x180012b56  jz      short loc_180012B81
0x180012b58  cmp     dword ptr [rcx+4], 1
0x180012b5c  jnz     short loc_180012B81
0x180012b5e  mov     r9, [rsp+0A8h+arg_28]; struct tagDISPPARAMS *
0x180012b66  mov     r8d, r13d; int
0x180012b69  mov     rdx, r12; struct IDispatch *
0x180012b6c  mov     [rsp+0A8h+var_88], rsi; struct CSession *
0x180012b71  call    ?JAmsiProcessor@JAmsi@@QEAAJPEAUIDispatch@@JPEAUtagDISPPARAMS@@PEAVCSession@@@Z; JAmsi::JAmsiProcessor(IDispatch *,long,tagDISPPARAMS *,CSession *)
0x180012b76  mov     r15d, eax
0x180012b79  test    eax, eax
0x180012b7b  js      loc_180012C6A
0x180012b81  mov     rdi, [rsi+3D8h]
0x180012b88  mov     qword ptr [rsp+0A8h+var_58], rdi
0x180012b8d  test    rdi, rdi
0x180012b90  jz      loc_180012E7F
0x180012b96  mov     rbp, [rdi+18h]
0x180012b9a  xor     r14d, r14d
0x180012b9d  mov     [rsp+0A8h+var_48], rbp
0x180012ba2  mov     qword ptr [rsp+0A8h+var_58+8], r14
0x180012ba7  test    rbp, rbp
0x180012baa  jz      short loc_180012BB0
0x180012bac  mov     [rdi+18h], r14
0x180012bb0  call    ?ClearFPUStatus@@YAXXZ; ClearFPUStatus(void)
0x180012bb5  mov     rax, [rbx]
0x180012bb8  test    rax, rax
0x180012bbb  jz      loc_180012CC1
0x180012bc1  cmp     dword ptr [rsi+3ECh], 0
0x180012bc8  mov     r8d, [rax+3F0h]; unsigned int
0x180012bcf  jl      loc_180012CDB
0x180012bd5  test    rbp, rbp
0x180012bd8  jz      short loc_180012BEA
0x180012bda  mov     rcx, [rbp+2C0h]; struct GL *
0x180012be1  test    rcx, rcx
0x180012be4  jnz     loc_180012D28
0x180012bea  mov     rcx, [rsp+0A8h+arg_40]
0x180012bf2  mov     edx, r13d
0x180012bf5  mov     rax, [r12]
0x180012bf9  movzx   r9d, [rsp+0A8h+arg_20]
0x180012c02  mov     [rsp+0A8h+var_70], rcx
0x180012c07  mov     rcx, [rsp+0A8h+arg_38]
0x180012c0f  mov     rax, [rax+40h]
0x180012c13  mov     [rsp+0A8h+var_78], rcx
0x180012c18  mov     rcx, [rsp+0A8h+arg_30]
0x180012c20  mov     [rsp+0A8h+var_80], rcx
0x180012c25  mov     rcx, [rsp+0A8h+arg_28]
0x180012c2d  mov     [rsp+0A8h+var_88], rcx
0x180012c32  mov     rcx, r12
0x180012c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c3a  mov     r15d, eax
0x180012c3d  test    rdi, rdi
0x180012c40  jz      short loc_180012C6A
0x180012c42  cmp     rbp, r14
0x180012c45  jz      short loc_180012C4C
0x180012c47  test    r14, r14
0x180012c4a  jnz     short loc_180012CAF
0x180012c4c  mov     [rdi+18h], rbp
0x180012c50  call    cs:__imp__statusfp
0x180012c56  test    eax, eax
0x180012c58  jnz     short loc_180012CA7
0x180012c5a  mov     edx, 30F031Fh; Mask
0x180012c5f  mov     ecx, 1Fh; NewValue
0x180012c64  call    cs:__imp__controlfp
0x180012c6a  cmp     byte ptr [rsp+0A8h+arg_18], 0
0x180012c72  jnz     short loc_180012C8C
0x180012c74  mov     r11, [rbx]
0x180012c77  test    r11, r11
0x180012c7a  jz      short loc_180012C8C
0x180012c7c  mov     r14, [r11+3A8h]
0x180012c83  test    r14, r14
0x180012c86  jnz     loc_180012D7C
0x180012c8c  mov     rbx, [rsp+0A8h+arg_8]
0x180012c94  mov     eax, r15d
0x180012c97  add     rsp, 70h
0x180012c9b  pop     r15
0x180012c9d  pop     r14
0x180012c9f  pop     r13
0x180012ca1  pop     r12
0x180012ca3  pop     rdi
0x180012ca4  pop     rsi
0x180012ca5  pop     rbp
0x180012ca6  retn
0x180012ca7  call    cs:__imp__clearfp
0x180012cad  jmp     short loc_180012C5A
0x180012caf  mov     rcx, r14; this
0x180012cb2  call    ?OnLeaveScript@COleScript@@QEAAXXZ; COleScript::OnLeaveScript(void)
0x180012cb7  mov     rcx, r14; this
0x180012cba  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x180012cbf  jmp     short loc_180012C4C
0x180012cc1  lea     rcx, [rsp+0A8h+var_58]; this
0x180012cc6  call    ?Close@TLS_NoDestructor@@QEAAXXZ; TLS_NoDestructor::Close(void)
0x180012ccb  mov     r15d, 8000FFFFh
0x180012cd1  jmp     short loc_180012C6A
0x180012cd3  mov     r15d, 8007000Eh
0x180012cd9  jmp     short loc_180012C6A
0x180012cdb  mov     rax, [rsp+0A8h+arg_40]
0x180012ce3  mov     edx, r13d; int
0x180012ce6  movzx   r9d, [rsp+0A8h+arg_20]; unsigned __int16
0x180012cef  mov     rcx, r12; struct IDispatchEx *
0x180012cf2  mov     [rsp+0A8h+var_70], rax; struct IServiceProvider *
0x180012cf7  mov     rax, [rsp+0A8h+arg_38]
0x180012cff  mov     [rsp+0A8h+var_78], rax; struct tagEXCEPINFO *
0x180012d04  mov     rax, [rsp+0A8h+arg_30]
0x180012d0c  mov     [rsp+0A8h+var_80], rax; struct tagVARIANT *
0x180012d11  mov     rax, [rsp+0A8h+arg_28]
0x180012d19  mov     [rsp+0A8h+var_88], rax; struct tagDISPPARAMS *
0x180012d1e  call    ?TrapIDispatchExInvokeEx@@YAJPEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z; TrapIDispatchExInvokeEx(IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)
0x180012d23  jmp     loc_180012C3A
0x180012d28  mov     rax, [rsp+0A8h+arg_40]
0x180012d30  mov     r9d, r8d; unsigned int
0x180012d33  mov     [rsp+0A8h+var_68], rax; struct IServiceProvider *
0x180012d38  mov     r8d, r13d; int
0x180012d3b  mov     rax, [rsp+0A8h+arg_38]
0x180012d43  mov     rdx, r12; struct IDispatchEx *
0x180012d46  mov     [rsp+0A8h+var_70], rax; struct tagEXCEPINFO *
0x180012d4b  mov     rax, [rsp+0A8h+arg_30]
0x180012d53  mov     [rsp+0A8h+var_78], rax; struct tagVARIANT *
0x180012d58  mov     rax, [rsp+0A8h+arg_28]
0x180012d60  mov     [rsp+0A8h+var_80], rax; struct tagDISPPARAMS *
0x180012d65  movzx   eax, [rsp+0A8h+arg_20]
0x180012d6d  mov     word ptr [rsp+0A8h+var_88], ax; unsigned __int16
0x180012d72  call    ?CatchIDispatchExInvokeEx@@YAJPEAVGL@@PEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z; CatchIDispatchExInvokeEx(GL *,IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)
0x180012d77  jmp     loc_180012C3A
0x180012d7c  mov     rcx, [rsi+50h]
0x180012d80  xor     ebx, ebx
0x180012d82  test    rcx, rcx
0x180012d85  jz      loc_180012ED8
0x180012d8b  xor     r8d, r8d
0x180012d8e  lea     rdx, [rcx+38h]
0x180012d92  xor     edi, edi
0x180012d94  test    rcx, rcx
0x180012d97  jz      loc_180012E35
0x180012d9d  mov     r10, [rcx+38h]
0x180012da1  test    r10, r10
0x180012da4  jz      loc_180012E76
0x180012daa  cmp     [rdx], rbx
0x180012dad  jz      loc_180012E76
0x180012db3  mov     rax, [r10]
0x180012db6  test    rax, rax
0x180012db9  jz      loc_180012E76
0x180012dbf  mov     r9, [rax+40h]
0x180012dc3  mov     r12, [rax+48h]
0x180012dc7  movsxd  rsi, dword ptr [r9+8]
0x180012dcb  add     rsi, r12
0x180012dce  jz      loc_180012E76
0x180012dd4  cmp     dword ptr [r9+0Ch], 20h ; ' '
0x180012dd9  jnz     loc_180012E76
0x180012ddf  mov     edx, [rcx+0A8h]
0x180012de5  test    edx, edx
0x180012de7  js      loc_180012ED1
0x180012ded  mov     rax, [r10+10h]
0x180012df1  cmp     edx, [rax+1Ch]
0x180012df4  jge     loc_180012ED1
0x180012dfa  mov     ecx, [rax+18h]
0x180012dfd  add     ecx, edx
0x180012dff  js      loc_180012ED1
0x180012e05  cmp     ecx, [r9+28h]
0x180012e09  jge     loc_180012ED1
0x180012e0f  movsxd  rax, dword ptr [r9+24h]
0x180012e13  add     rax, r12
0x180012e16  movsxd  rcx, ecx
0x180012e19  mov     rcx, [rax+rcx*8]
0x180012e1d  mov     [rsp+0A8h+arg_0], rcx
0x180012e25  mov     r8d, ecx
0x180012e28  mov     eax, dword ptr [rsp+0A8h+arg_0+4]
0x180012e2f  mov     ebx, [rsi]
0x180012e31  lea     edi, [rax+r8]
0x180012e35  mov     rdx, [r14]
0x180012e38  mov     r9d, ebx
0x180012e3b  movups  xmm0, xmmword ptr [r11+3B0h]
0x180012e43  mov     [rsp+0A8h+var_78], 0
0x180012e4c  mov     rcx, r14
0x180012e4f  mov     dword ptr [rsp+0A8h+var_80], edi
0x180012e53  mov     rax, [rdx+18h]
0x180012e57  mov     edx, 3
0x180012e5c  mov     dword ptr [rsp+0A8h+var_88], r8d
0x180012e61  lea     r8, [rsp+0A8h+var_58]
0x180012e66  movdqu  [rsp+0A8h+var_58], xmm0
0x180012e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e71  jmp     loc_180012C8C
0x180012e76  mov     rcx, [rcx+10h]
0x180012e7a  jmp     loc_180012D94
0x180012e7f  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180012e85  call    cs:__imp_TlsGetValue
0x180012e8b  mov     qword ptr [rsp+0A8h+var_58], rax
0x180012e90  mov     rdi, rax
0x180012e93  test    rax, rax
0x180012e96  jnz     loc_180012B96
0x180012e9c  mov     rbp, [rsp+0A8h+var_48]
0x180012ea1  mov     r14, qword ptr [rsp+0A8h+var_58+8]
0x180012ea6  jmp     loc_180012BB5
0x180012eab  call    ?IsResponseDotWrite@CSession@@QEAA_NPEAUIDispatch@@J@Z; CSession::IsResponseDotWrite(IDispatch *,long)
0x180012eb0  mov     byte ptr [rsp+0A8h+arg_18], al
0x180012eb7  test    al, al
0x180012eb9  jnz     loc_180012B2A
0x180012ebf  mov     edx, 2; enum tagSCRIPTTRACEINFO
0x180012ec4  mov     rcx, rsi; this
0x180012ec7  call    ?SendRuntimeScriptInfoToHost@CSession@@QEAAJW4tagSCRIPTTRACEINFO@@@Z; CSession::SendRuntimeScriptInfoToHost(tagSCRIPTTRACEINFO)
0x180012ecc  jmp     loc_180012B2A
0x180012ed1  xor     eax, eax
0x180012ed3  jmp     loc_180012E2F
0x180012ed8  xor     edi, edi
0x180012eda  xor     r8d, r8d
0x180012edd  jmp     loc_180012E35
```
