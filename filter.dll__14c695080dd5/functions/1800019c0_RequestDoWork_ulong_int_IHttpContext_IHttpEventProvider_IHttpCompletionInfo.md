# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x1800019c0`
- end: `0x180001d11`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `849`
- prototype: `__int64 __fastcall(int, int, __int64 *, struct ISendResponseProvider *, __int64)`
- caller_count: `29`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180001900`
- `0x180001930`
- `0x180001960`
- `0x180001990`
- `0x180008890`
- `0x180009380`
- `0x1800093f0`
- `0x1800094a0`
- `0x180009510`
- `0x180009580`
- `0x1800095f0`
- `0x180009660`
- `0x1800097b0`
- `0x1800098a0`
- `0x180009950`
- `0x1800099c0`
- `0x180009a30`
- `0x180009aa0`
- `0x180009b10`
- `0x180009b80`
- `0x180009bf0`
- `0x180009c60`
- `0x180009cd0`
- `0x180009d40`
- `0x180009d70`
- `0x180009da0`
- `0x180009e10`
- `0x180009e80`
- `0x180009f70`

## callees

- `0x180001320`
- `0x1800019c0`
- `0x180001d20`
- `0x180002a40`
- `0x180002c60`
- `0x180007490`
- `0x1800074c0`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall RequestDoWork(int a1, int a2, __int64 *a3, struct ISendResponseProvider *a4, __int64 a5)
{
  __int64 v5; // rax
  __int64 v10; // rax
  __int64 (__fastcall ***v11)(_QWORD, void *); // rax
  __int64 v12; // rax
  __int64 v13; // rbx
  _DWORD *v14; // rax
  int v15; // eax
  int v16; // eax
  _DWORD *v17; // rsi
  _DWORD *v18; // rax
  int v19; // eax
  int v20; // eax
  int v22; // eax
  int v23; // ebx
  __int64 v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // eax
  bool v27; // zf
  __int64 (__fastcall *v28)(__int64 *); // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  const char *v31; // r8
  int v32; // eax
  __int64 v33; // r9
  int v34; // [rsp+40h] [rbp-48h] BYREF
  int v35[17]; // [rsp+44h] [rbp-44h] BYREF
  int v36; // [rsp+A0h] [rbp+18h] BYREF

  v5 = *a3;
  v36 = 0;
  v34 = 0;
  v35[0] = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *))(v5 + 240))(a3);
  v11 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 56LL))(v10);
  v12 = (**v11)(v11, g_pFilterModuleContext);
  v13 = v12;
  if ( !v12 )
  {
    if ( a1 == 2 && !a2 )
      (*(void (__fastcall **)(__int64 *, __int64, __int64))(*a3 + 80))(a3, 2684354560LL, 2);
    return 0;
  }
  *(_QWORD *)(v12 + 24) = a3;
  if ( a1 != 2 )
  {
    if ( a1 == 0x20000000 )
    {
      v22 = W3_FILTER_CONTEXT::HandleSendResponse((W3_FILTER_CONTEXT *)v12, a4, &v36);
    }
    else
    {
      if ( a1 != 0x80000000 )
      {
        v23 = 0;
LABEL_25:
        if ( !v36 )
          return 0;
LABEL_26:
        v24 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 32))(a3);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 96LL))(v24);
        if ( v23 < 0 )
        {
          (**(void (__fastcall ***)(struct ISendResponseProvider *, _QWORD))a4)(a4, (unsigned int)v23);
          v25 = WIN32_FROM_HRESULT(v23) - 2;
          if ( v25 && (v26 = v25 - 1) != 0 )
          {
            v27 = v26 == 2;
            v28 = *(__int64 (__fastcall **)(__int64 *))(*a3 + 32);
            if ( v27 )
            {
              v29 = v28(a3);
              v30 = 401;
              v31 = "Unauthorized";
              v33 = 4;
LABEL_58:
              (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v29 + 24LL))(
                v29,
                v30,
                v31,
                v33,
                v23,
                0,
                0);
              return 2;
            }
            v29 = v28(a3);
            v30 = 500;
            v31 = "Internal Server Error";
          }
          else
          {
            v29 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 32))(a3);
            v30 = 404;
            v31 = "Not Found";
          }
          v33 = 0;
          goto LABEL_58;
        }
        return 2;
      }
      v22 = W3_FILTER_CONTEXT::HandleOnUrlMap((W3_FILTER_CONTEXT *)v12, a4, &v36);
    }
    goto LABEL_23;
  }
  if ( !a2 )
  {
    if ( *(_DWORD *)(v12 + 256) || (v14 = *(_DWORD **)(v12 + 112)) == 0 )
    {
      v17 = (_DWORD *)(v13 + 60);
      if ( *(_DWORD *)(v13 + 60) )
        v32 = *(_DWORD *)(v13 + 148);
      else
        v32 = *(_DWORD *)(v13 + 152);
      v16 = v32 & 0x1000;
    }
    else
    {
      if ( v14[4] )
      {
        if ( *(_DWORD *)(v13 + 60) )
          v15 = v14[32];
        else
          v15 = v14[18];
        v16 = v15 & 0x1000;
      }
      else
      {
        v16 = 0;
      }
      v17 = (_DWORD *)(v13 + 60);
    }
    if ( !v16 )
      (*(void (__fastcall **)(__int64 *, __int64, _QWORD))(*a3 + 80))(a3, 0x80000000LL, 0);
    if ( *(_DWORD *)(v13 + 256) || (v18 = *(_DWORD **)(v13 + 112)) == 0 )
    {
      if ( *v17 )
        v19 = *(_DWORD *)(v13 + 148);
      else
        v19 = *(_DWORD *)(v13 + 152);
    }
    else
    {
      if ( !v18[4] )
      {
        v20 = 0;
        goto LABEL_19;
      }
      if ( *v17 )
        v19 = v18[32];
      else
        v19 = v18[18];
    }
    v20 = v19 & 0x2000;
LABEL_19:
    if ( !v20 )
      return 0;
    v22 = W3_FILTER_CONTEXT::HandleOnAuthenticate((W3_FILTER_CONTEXT *)v13, &v36);
LABEL_23:
    v23 = v22;
    goto LABEL_24;
  }
  if ( a5 )
  {
    W3_FILTER_CONTEXT::HandleAuthCompleteCompletion((W3_FILTER_CONTEXT *)v12);
    return 2;
  }
  v23 = W3_FILTER_CONTEXT::HandleAuthComplete((W3_FILTER_CONTEXT *)v12, &v36, &v34, v35);
  if ( !v34 )
  {
LABEL_24:
    if ( v23 < 0 )
      goto LABEL_26;
    goto LABEL_25;
  }
  if ( !v35[0] )
    return 2;
  return 1;
}

```

## disassembly

```asm
0x1800019c0  push    rbx
0x1800019c2  push    rbp
0x1800019c3  push    rsi
0x1800019c4  push    rdi
0x1800019c5  push    r14
0x1800019c7  push    r15
0x1800019c9  sub     rsp, 58h
0x1800019cd  mov     rax, [r8]
0x1800019d0  xor     r15d, r15d
0x1800019d3  mov     esi, ecx
0x1800019d5  mov     [rsp+88h+arg_10], r15d
0x1800019dd  mov     rcx, r8
0x1800019e0  mov     [rsp+88h+var_48], r15d
0x1800019e5  mov     r14, r9
0x1800019e8  mov     [rsp+88h+var_44], r15d
0x1800019ed  mov     rax, [rax+0F0h]
0x1800019f4  mov     rdi, r8
0x1800019f7  mov     ebp, edx
0x1800019f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019fe  mov     rcx, rax
0x180001a01  mov     r8, [rax]
0x180001a04  mov     rax, [r8+38h]
0x180001a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a0d  mov     rdx, cs:?g_pFilterModuleContext@@3PEAXEA; void * g_pFilterModuleContext
0x180001a14  mov     r8, rax
0x180001a17  mov     rcx, [rax]
0x180001a1a  mov     rax, [rcx]
0x180001a1d  mov     rcx, r8
0x180001a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a25  mov     rbx, rax
0x180001a28  test    rax, rax
0x180001a2b  jz      loc_180001C29
0x180001a31  mov     [rax+18h], rdi
0x180001a35  cmp     esi, 2
0x180001a38  jnz     loc_180001AE7
0x180001a3e  test    ebp, ebp
0x180001a40  jnz     loc_180001B91
0x180001a46  cmp     [rax+100h], r15d
0x180001a4d  jnz     loc_180001C66
0x180001a53  mov     rax, [rax+70h]
0x180001a57  test    rax, rax
0x180001a5a  jz      loc_180001C66
0x180001a60  cmp     [rax+10h], r15d
0x180001a64  jz      loc_180001C5E
0x180001a6a  cmp     [rbx+3Ch], r15d
0x180001a6e  jnz     loc_180001BDE
0x180001a74  mov     eax, [rax+48h]
0x180001a77  and     eax, 1000h
0x180001a7c  lea     rsi, [rbx+3Ch]
0x180001a80  test    eax, eax
0x180001a82  jnz     short loc_180001A9B
0x180001a84  mov     rax, [rdi]
0x180001a87  xor     r8d, r8d
0x180001a8a  mov     edx, 80000000h
0x180001a8f  mov     rcx, rdi
0x180001a92  mov     rax, [rax+50h]
0x180001a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a9b  cmp     [rbx+100h], r15d
0x180001aa2  jnz     loc_180001C90
0x180001aa8  mov     rax, [rbx+70h]
0x180001aac  test    rax, rax
0x180001aaf  jz      loc_180001C90
0x180001ab5  cmp     [rax+10h], r15d
0x180001ab9  jz      loc_180001C88
0x180001abf  cmp     [rsi], r15d
0x180001ac2  jnz     loc_180001BE9
0x180001ac8  mov     eax, [rax+48h]
0x180001acb  and     eax, 2000h
0x180001ad0  test    eax, eax
0x180001ad2  jnz     loc_180001C14
0x180001ad8  xor     eax, eax
0x180001ada  add     rsp, 58h
0x180001ade  pop     r15
0x180001ae0  pop     r14
0x180001ae2  pop     rdi
0x180001ae3  pop     rsi
0x180001ae4  pop     rbp
0x180001ae5  pop     rbx
0x180001ae6  retn
0x180001ae7  cmp     esi, 20000000h
0x180001aed  jnz     loc_180001BF4
0x180001af3  lea     r8, [rsp+88h+arg_10]; int *
0x180001afb  mov     rdx, r14; struct ISendResponseProvider *
0x180001afe  mov     rcx, rbx; this
0x180001b01  call    ?HandleSendResponse@W3_FILTER_CONTEXT@@QEAAJPEAVISendResponseProvider@@PEAH@Z; W3_FILTER_CONTEXT::HandleSendResponse(ISendResponseProvider *,int *)
0x180001b06  mov     ebx, eax
0x180001b08  test    ebx, ebx
0x180001b0a  js      short loc_180001B16
0x180001b0c  cmp     [rsp+88h+arg_10], r15d
0x180001b14  jz      short loc_180001AD8
0x180001b16  mov     rax, [rdi]
0x180001b19  mov     rcx, rdi
0x180001b1c  mov     rax, [rax+20h]
0x180001b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b25  mov     rdx, rax
0x180001b28  mov     rcx, [rax]
0x180001b2b  mov     rax, [rcx+60h]
0x180001b2f  mov     rcx, rdx
0x180001b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b37  test    ebx, ebx
0x180001b39  jns     loc_180001BCD
0x180001b3f  mov     rax, [r14]
0x180001b42  mov     edx, ebx
0x180001b44  mov     rcx, r14
0x180001b47  mov     rax, [rax]
0x180001b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b4f  mov     ecx, ebx; int
0x180001b51  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180001b56  sub     eax, 2
0x180001b59  jz      loc_180001CCE
0x180001b5f  sub     eax, 1
0x180001b62  jz      loc_180001CCE
0x180001b68  cmp     eax, 2
0x180001b6b  mov     rcx, rdi
0x180001b6e  mov     rax, [rdi]
0x180001b71  mov     rax, [rax+20h]
0x180001b75  jz      loc_180001CB5
0x180001b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b80  mov     edx, 1F4h
0x180001b85  lea     r8, aInternalServer; "Internal Server Error"
0x180001b8c  jmp     loc_180001CE9
0x180001b91  mov     rcx, rbx; this
0x180001b94  cmp     [rsp+88h+arg_20], r15
0x180001b9c  jnz     short loc_180001BD7
0x180001b9e  lea     r9, [rsp+88h+var_44]; int *
0x180001ba3  lea     r8, [rsp+88h+var_48]; int *
0x180001ba8  lea     rdx, [rsp+88h+arg_10]; int *
0x180001bb0  call    ?HandleAuthComplete@W3_FILTER_CONTEXT@@QEAAJPEAH00@Z; W3_FILTER_CONTEXT::HandleAuthComplete(int *,int *,int *)
0x180001bb5  mov     ebx, eax
0x180001bb7  cmp     [rsp+88h+var_48], r15d
0x180001bbc  jz      loc_180001B08
0x180001bc2  cmp     [rsp+88h+var_44], r15d
0x180001bc7  jnz     loc_180001CAB
0x180001bcd  mov     eax, 2
0x180001bd2  jmp     loc_180001ADA
0x180001bd7  call    ?HandleAuthCompleteCompletion@W3_FILTER_CONTEXT@@QEAAXXZ; W3_FILTER_CONTEXT::HandleAuthCompleteCompletion(void)
0x180001bdc  jmp     short loc_180001BCD
0x180001bde  mov     eax, [rax+80h]
0x180001be4  jmp     loc_180001A77
0x180001be9  mov     eax, [rax+80h]
0x180001bef  jmp     loc_180001ACB
0x180001bf4  cmp     esi, 80000000h
0x180001bfa  jnz     short loc_180001C56
0x180001bfc  lea     r8, [rsp+88h+arg_10]; int *
0x180001c04  mov     rdx, r14; struct IMapPathProvider *
0x180001c07  mov     rcx, rbx; this
0x180001c0a  call    ?HandleOnUrlMap@W3_FILTER_CONTEXT@@QEAAJPEAVIMapPathProvider@@PEAH@Z; W3_FILTER_CONTEXT::HandleOnUrlMap(IMapPathProvider *,int *)
0x180001c0f  jmp     loc_180001B06
0x180001c14  lea     rdx, [rsp+88h+arg_10]; int *
0x180001c1c  mov     rcx, rbx; this
0x180001c1f  call    ?HandleOnAuthenticate@W3_FILTER_CONTEXT@@QEAAJPEAH@Z; W3_FILTER_CONTEXT::HandleOnAuthenticate(int *)
0x180001c24  jmp     loc_180001B06
0x180001c29  cmp     esi, 2
0x180001c2c  jnz     loc_180001AD8
0x180001c32  test    ebp, ebp
0x180001c34  jnz     loc_180001AD8
0x180001c3a  mov     rax, [rdi]
0x180001c3d  mov     edx, 0A0000000h
0x180001c42  mov     r8d, esi
0x180001c45  mov     rcx, rdi
0x180001c48  mov     rax, [rax+50h]
0x180001c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c51  jmp     loc_180001AD8
0x180001c56  mov     ebx, r15d
0x180001c59  jmp     loc_180001B0C
0x180001c5e  mov     eax, r15d
0x180001c61  jmp     loc_180001A7C
0x180001c66  cmp     [rbx+3Ch], r15d
0x180001c6a  lea     rsi, [rbx+3Ch]
0x180001c6e  jnz     short loc_180001C78
0x180001c70  mov     eax, [rbx+98h]
0x180001c76  jmp     short loc_180001C7E
0x180001c78  mov     eax, [rbx+94h]
0x180001c7e  and     eax, 1000h
0x180001c83  jmp     loc_180001A80
0x180001c88  mov     eax, r15d
0x180001c8b  jmp     loc_180001AD0
0x180001c90  cmp     [rsi], r15d
0x180001c93  jnz     short loc_180001CA0
0x180001c95  mov     eax, [rbx+98h]
0x180001c9b  jmp     loc_180001ACB
0x180001ca0  mov     eax, [rbx+94h]
0x180001ca6  jmp     loc_180001ACB
0x180001cab  mov     eax, 1
0x180001cb0  jmp     loc_180001ADA
0x180001cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cba  mov     edx, 191h
0x180001cbf  lea     r8, aUnauthorized; "Unauthorized"
0x180001cc6  mov     r9d, 4
0x180001ccc  jmp     short loc_180001CEC
0x180001cce  mov     rax, [rdi]
0x180001cd1  mov     rcx, rdi
0x180001cd4  mov     rax, [rax+20h]
0x180001cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cdd  mov     edx, 194h
0x180001ce2  lea     r8, aNotFound; "Not Found"
0x180001ce9  xor     r9d, r9d
0x180001cec  mov     rcx, [rax]
0x180001cef  mov     r10, rax
0x180001cf2  mov     [rsp+88h+var_58], r15d
0x180001cf7  mov     [rsp+88h+var_60], r15
0x180001cfc  mov     [rsp+88h+var_68], ebx
0x180001d00  mov     rax, [rcx+18h]
0x180001d04  mov     rcx, r10
0x180001d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d0c  jmp     loc_180001BCD
```
