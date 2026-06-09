# IIS_MODULE::BeginReceiveEntity(int *)

- ea: `0x18000b3ac`
- end: `0x18000b55e`
- name: `?BeginReceiveEntity@IIS_MODULE@@AEAAJPEAH@Z`
- size: `434`
- prototype: `__int64 __fastcall(IIS_MODULE *__hidden this, int *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000cb30`
- `0x18000cfa0`
- `0x18000e3b0`

## callees

- `0x180006bcc`
- `0x180008f90`
- `0x180009128`
- `0x18000b3ac`
- `0x18000df0c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall IIS_MODULE::BeginReceiveEntity(IIS_MODULE *this, int *a2)
{
  struct FCGI_BUFFER *v4; // rax
  unsigned int v5; // edi
  FCGI_BUFFER *v6; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  struct IHttpTraceContext *v14; // rbx
  const struct _GUID *v15; // rdx
  GUID *v16; // [rsp+40h] [rbp-28h] BYREF
  __int128 v17; // [rsp+48h] [rbp-20h]
  int v18; // [rsp+70h] [rbp+8h] BYREF

  v18 = 0;
  *a2 = 0;
  v4 = FCGI_BUFFER::Alloc(0x2000);
  *((_QWORD *)this + 17) = v4;
  if ( !v4 )
  {
    v5 = -2147024882;
LABEL_3:
    v6 = (FCGI_BUFFER *)*((_QWORD *)this + 17);
    if ( v6 )
    {
      FCGI_BUFFER::Free(v6);
      *((_QWORD *)this + 17) = 0;
    }
    return v5;
  }
  *((_DWORD *)v4 + 7) = 3;
  v8 = *((_QWORD *)this + 21);
  *((_DWORD *)this + 23) = 1;
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)v9 + 128LL))(
          v9,
          **((_QWORD **)this + 17),
          *(unsigned int *)(*((_QWORD *)this + 17) + 8LL),
          1,
          0,
          0);
  v5 = v10;
  if ( v10 >= 0 )
    return v5;
  *((_DWORD *)this + 23) = 0;
  if ( v10 != -2147024858 )
    goto LABEL_3;
  v11 = *((_QWORD *)this + 17);
  *(_QWORD *)(v11 + 16) = *(_QWORD *)v11;
  *(_DWORD *)(v11 + 24) = 0;
  v12 = APPLICATION::SendFcgiStdIn(*((APPLICATION **)this + 5), *((struct FCGI_BUFFER **)this + 17), &v18);
  *((_QWORD *)this + 17) = 0;
  v5 = v12;
  if ( v12 < 0 )
    goto LABEL_3;
  v13 = *((_QWORD *)this + 21);
  *((_DWORD *)this + 37) = 0;
  *a2 = 1;
  v14 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 272LL))(v13);
  v16 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v17 = 0;
  if ( (**(int (__fastcall ***)(struct IHttpTraceContext *, GUID **))v14)(v14, &v16) >= 0
    && DWORD2(v17)
    && DWORD1(v17) >= 5
    && ((_DWORD)v17 == 4096 || (v17 & 0x1000) != 0) )
  {
    IISFastCGIEvents::FASTCGI_WAITING_FOR_RESPONSE::RaiseEvent(v14, v15);
  }
  return v5;
}

```

## disassembly

```asm
0x18000b3ac  mov     [rsp+arg_8], rbx
0x18000b3b1  mov     [rsp+arg_10], rsi
0x18000b3b6  push    rdi
0x18000b3b7  sub     rsp, 60h
0x18000b3bb  mov     rbx, rcx
0x18000b3be  mov     [rsp+68h+arg_0], 0
0x18000b3c6  mov     ecx, 2000h; unsigned int
0x18000b3cb  mov     dword ptr [rdx], 0
0x18000b3d1  mov     rsi, rdx
0x18000b3d4  call    ?Alloc@FCGI_BUFFER@@SAPEAV1@K@Z; FCGI_BUFFER::Alloc(ulong)
0x18000b3d9  mov     [rbx+88h], rax
0x18000b3e0  test    rax, rax
0x18000b3e3  jnz     short loc_18000B41A
0x18000b3e5  mov     edi, 8007000Eh
0x18000b3ea  mov     rcx, [rbx+88h]; this
0x18000b3f1  test    rcx, rcx
0x18000b3f4  jz      short loc_18000B406
0x18000b3f6  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x18000b3fb  mov     qword ptr [rbx+88h], 0
0x18000b406  lea     r11, [rsp+68h+var_8]
0x18000b40b  mov     eax, edi
0x18000b40d  mov     rbx, [r11+18h]
0x18000b411  mov     rsi, [r11+20h]
0x18000b415  mov     rsp, r11
0x18000b418  pop     rdi
0x18000b419  retn
0x18000b41a  mov     dword ptr [rax+1Ch], 3
0x18000b421  mov     rcx, [rbx+0A8h]
0x18000b428  mov     dword ptr [rbx+5Ch], 1
0x18000b42f  mov     rax, [rcx]
0x18000b432  mov     rax, [rax+18h]
0x18000b436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b43b  mov     rdx, [rbx+88h]
0x18000b442  mov     r10, rax
0x18000b445  mov     [rsp+68h+var_40], 0
0x18000b44e  mov     r9d, 1
0x18000b454  mov     [rsp+68h+var_48], 0
0x18000b45d  mov     rcx, [rax]
0x18000b460  mov     r8d, [rdx+8]
0x18000b464  mov     rdx, [rdx]
0x18000b467  mov     rax, [rcx+80h]
0x18000b46e  mov     rcx, r10
0x18000b471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b476  mov     edi, eax
0x18000b478  test    eax, eax
0x18000b47a  jns     short loc_18000B406
0x18000b47c  mov     dword ptr [rbx+5Ch], 0
0x18000b483  cmp     eax, 80070026h
0x18000b488  jnz     loc_18000B3EA
0x18000b48e  mov     rcx, [rbx+88h]
0x18000b495  lea     r8, [rsp+68h+arg_0]; int *
0x18000b49a  mov     rax, [rcx]
0x18000b49d  mov     [rcx+10h], rax
0x18000b4a1  mov     dword ptr [rcx+18h], 0
0x18000b4a8  mov     rdx, [rbx+88h]; struct FCGI_BUFFER *
0x18000b4af  mov     rcx, [rbx+28h]; this
0x18000b4b3  call    ?SendFcgiStdIn@APPLICATION@@QEAAJPEAVFCGI_BUFFER@@PEAH@Z; APPLICATION::SendFcgiStdIn(FCGI_BUFFER *,int *)
0x18000b4b8  mov     qword ptr [rbx+88h], 0
0x18000b4c3  mov     edi, eax
0x18000b4c5  test    eax, eax
0x18000b4c7  js      loc_18000B3EA
0x18000b4cd  mov     rcx, [rbx+0A8h]
0x18000b4d4  mov     dword ptr [rbx+94h], 0
0x18000b4de  mov     dword ptr [rsi], 1
0x18000b4e4  mov     rax, [rcx]
0x18000b4e7  mov     rax, [rax+110h]
0x18000b4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4f3  mov     rbx, rax
0x18000b4f6  lea     rdx, [rsp+68h+var_28]
0x18000b4fb  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000b502  xorps   xmm0, xmm0
0x18000b505  mov     [rsp+68h+var_28], rax
0x18000b50a  movdqu  [rsp+68h+var_20], xmm0
0x18000b510  mov     rcx, [rbx]
0x18000b513  mov     rax, [rcx]
0x18000b516  mov     rcx, rbx
0x18000b519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b51e  test    eax, eax
0x18000b520  js      loc_18000B406
0x18000b526  cmp     dword ptr [rsp+68h+var_20+8], 0
0x18000b52b  jz      loc_18000B406
0x18000b531  cmp     dword ptr [rsp+68h+var_20+4], 5
0x18000b536  jb      loc_18000B406
0x18000b53c  mov     eax, 1000h
0x18000b541  cmp     dword ptr [rsp+68h+var_20], eax
0x18000b545  jz      short loc_18000B551
0x18000b547  test    dword ptr [rsp+68h+var_20], eax
0x18000b54b  jz      loc_18000B406
0x18000b551  mov     rcx, rbx; struct IHttpTraceContext *
0x18000b554  call    ?RaiseEvent@FASTCGI_WAITING_FOR_RESPONSE@IISFastCGIEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISFastCGIEvents::FASTCGI_WAITING_FOR_RESPONSE::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x18000b559  jmp     loc_18000B406
```
