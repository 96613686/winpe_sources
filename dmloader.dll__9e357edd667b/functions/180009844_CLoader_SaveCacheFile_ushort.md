# CLoader::SaveCacheFile(ushort *)

- ea: `0x180009844`
- end: `0x1800099d9`
- name: `?SaveCacheFile@CLoader@@AEAAJPEAG@Z`
- size: `405`
- prototype: `__int64 __fastcall(CLoader *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800099e0`

## callees

- `0x1800015d0`
- `0x180009844`
- `0x18000ba54`
- `0x18000cd7c`
- `0x18000d80c`
- `0x18000db40`
- `0x18000df2c`
- `0x180010010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009883`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009883`

## pseudocode

```c
__int64 __fastcall CLoader::SaveCacheFile(CClass **this, unsigned __int16 *a2)
{
  int v4; // edi
  CFileStream *v5; // rax
  CFileStream *v6; // rax
  CFileStream *v7; // rbx
  struct IRIFFStream *v8; // rsi
  CClass *i; // r14
  struct IRIFFStream *v11; // [rsp+20h] [rbp-40h] BYREF
  __int64 v12; // [rsp+28h] [rbp-38h] BYREF
  int v13; // [rsp+30h] [rbp-30h]
  __int64 v14; // [rsp+34h] [rbp-2Ch]
  __int128 v15; // [rsp+40h] [rbp-20h] BYREF
  int v16; // [rsp+50h] [rbp-10h]

  v15 = 0;
  v16 = 0;
  v4 = -2147024882;
  v5 = (CFileStream *)malloc(0x230u);
  if ( v5 )
  {
    v6 = CFileStream::CFileStream(v5, (struct CLoader *)this);
    v7 = v6;
    if ( v6 )
    {
      v4 = CFileStream::Open(v6, a2, 0x40000000);
      if ( v4 >= 0 )
      {
        v11 = 0;
        v4 = AllocRIFFStream(v7, &v11);
        if ( v4 >= 0 )
        {
          v8 = v11;
          DWORD2(v15) = 1129073988;
          if ( !(*(unsigned int (__fastcall **)(struct IRIFFStream *, __int128 *, __int64))(*(_QWORD *)v11 + 40LL))(
                  v11,
                  &v15,
                  32) )
          {
            v12 = 0;
            v14 = 0;
            v13 = 1819503715;
            if ( !(*(unsigned int (__fastcall **)(struct IRIFFStream *, __int64 *, __int64))(*(_QWORD *)v8 + 40LL))(
                    v8,
                    &v12,
                    64) )
            {
              for ( i = this[3]; i; i = *(CClass **)i )
              {
                v4 = CClass::SaveToCache(i, v8);
                if ( v4 < 0 )
                  goto LABEL_15;
              }
              if ( (*(unsigned int (__fastcall **)(struct IRIFFStream *, __int64 *, _QWORD))(*(_QWORD *)v8 + 32LL))(
                     v8,
                     &v12,
                     0) )
              {
                v4 = -2005397227;
              }
            }
            if ( (*(unsigned int (__fastcall **)(struct IRIFFStream *, __int128 *, _QWORD))(*(_QWORD *)v8 + 32LL))(
                   v8,
                   &v15,
                   0) )
            {
              v4 = -2005397227;
            }
          }
LABEL_15:
          (*(void (__fastcall **)(struct IRIFFStream *))(*(_QWORD *)v8 + 16LL))(v8);
        }
      }
      CFileStream::Release(v7);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009844  mov     [rsp-18h+arg_10], rbx
0x180009849  mov     [rsp-18h+arg_18], rsi
0x18000984e  push    rbp
0x18000984f  push    rdi
0x180009850  push    r14
0x180009852  mov     rbp, rsp
0x180009855  sub     rsp, 60h
0x180009859  mov     rax, cs:__security_cookie
0x180009860  xor     rax, rsp
0x180009863  mov     [rbp+var_8], rax
0x180009867  mov     r14, rcx
0x18000986a  xorps   xmm0, xmm0
0x18000986d  xor     eax, eax
0x18000986f  mov     ecx, 230h; Size
0x180009874  movups  [rbp+var_20], xmm0
0x180009878  mov     [rbp+var_10], eax
0x18000987b  mov     rsi, rdx
0x18000987e  mov     edi, 8007000Eh
0x180009883  call    cs:__imp_malloc
0x180009889  test    rax, rax
0x18000988c  jz      loc_1800099B6
0x180009892  mov     rdx, r14; struct CLoader *
0x180009895  mov     rcx, rax; this
0x180009898  call    ??0CFileStream@@QEAA@PEAVCLoader@@@Z; CFileStream::CFileStream(CLoader *)
0x18000989d  mov     rbx, rax
0x1800098a0  test    rax, rax
0x1800098a3  jz      loc_1800099B6
0x1800098a9  mov     r8d, 40000000h; unsigned int
0x1800098af  mov     rdx, rsi; unsigned __int16 *
0x1800098b2  mov     rcx, rax; this
0x1800098b5  call    ?Open@CFileStream@@QEAAJPEAGK@Z; CFileStream::Open(ushort *,ulong)
0x1800098ba  mov     edi, eax
0x1800098bc  test    eax, eax
0x1800098be  js      loc_1800099AE
0x1800098c4  lea     rdx, [rbp+var_40]
0x1800098c8  mov     [rbp+var_40], 0
0x1800098d0  mov     rcx, rbx
0x1800098d3  call    AllocRIFFStream
0x1800098d8  mov     edi, eax
0x1800098da  test    eax, eax
0x1800098dc  js      loc_1800099AE
0x1800098e2  mov     rsi, [rbp+var_40]
0x1800098e6  lea     rdx, [rbp+var_20]
0x1800098ea  mov     dword ptr [rbp+var_20+8], 434C4D44h
0x1800098f1  mov     r8d, 20h ; ' '
0x1800098f7  mov     rcx, rsi
0x1800098fa  mov     rax, [rsi]
0x1800098fd  mov     rax, [rax+28h]
0x180009901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009906  test    eax, eax
0x180009908  jnz     loc_18000999F
0x18000990e  mov     [rbp+var_38], 0
0x180009916  lea     rdx, [rbp+var_38]
0x18000991a  mov     [rbp+var_2C], 0
0x180009922  mov     r8d, 40h ; '@'
0x180009928  mov     [rbp+var_30], 6C736C63h
0x18000992f  mov     rcx, rsi
0x180009932  mov     rax, [rsi]
0x180009935  mov     rax, [rax+28h]
0x180009939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000993e  test    eax, eax
0x180009940  jnz     short loc_180009980
0x180009942  mov     r14, [r14+18h]
0x180009946  jmp     short loc_18000995C
0x180009948  mov     rdx, rsi; struct IRIFFStream *
0x18000994b  mov     rcx, r14; this
0x18000994e  call    ?SaveToCache@CClass@@QEAAJPEAUIRIFFStream@@@Z; CClass::SaveToCache(IRIFFStream *)
0x180009953  mov     edi, eax
0x180009955  test    eax, eax
0x180009957  js      short loc_18000999F
0x180009959  mov     r14, [r14]
0x18000995c  test    r14, r14
0x18000995f  jnz     short loc_180009948
0x180009961  mov     rax, [rsi]
0x180009964  lea     rdx, [rbp+var_38]
0x180009968  xor     r8d, r8d
0x18000996b  mov     rcx, rsi
0x18000996e  mov     rax, [rax+20h]
0x180009972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009977  test    eax, eax
0x180009979  jz      short loc_180009980
0x18000997b  mov     edi, 88781115h
0x180009980  mov     rax, [rsi]
0x180009983  lea     rdx, [rbp+var_20]
0x180009987  xor     r8d, r8d
0x18000998a  mov     rcx, rsi
0x18000998d  mov     rax, [rax+20h]
0x180009991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009996  test    eax, eax
0x180009998  jz      short loc_18000999F
0x18000999a  mov     edi, 88781115h
0x18000999f  mov     rax, [rsi]
0x1800099a2  mov     rcx, rsi
0x1800099a5  mov     rax, [rax+10h]
0x1800099a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ae  mov     rcx, rbx; this
0x1800099b1  call    ?Release@CFileStream@@UEAAKXZ; CFileStream::Release(void)
0x1800099b6  mov     eax, edi
0x1800099b8  mov     rcx, [rbp+var_8]
0x1800099bc  xor     rcx, rsp; StackCookie
0x1800099bf  call    __security_check_cookie
0x1800099c4  lea     r11, [rsp+60h+var_s0]
0x1800099c9  mov     rbx, [r11+30h]
0x1800099cd  mov     rsi, [r11+38h]
0x1800099d1  mov     rsp, r11
0x1800099d4  pop     r14
0x1800099d6  pop     rdi
0x1800099d7  pop     rbp
0x1800099d8  retn
```
