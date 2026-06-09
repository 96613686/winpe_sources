# CContentSnippetBuilder::BuildContentSnippetProperty(tagPROPVARIANT *)

- ea: `0x1800a5810`
- end: `0x1800a593c`
- name: `?BuildContentSnippetProperty@CContentSnippetBuilder@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(CContentSnippetBuilder *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18008e690`
- `0x1800a5810`
- `0x1800a5944`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800a5845`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800a5845`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800a5871`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800a58b7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800a58d7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800a5871`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800a58b7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800a58d7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800a58ff`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800a58ff`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x1800a58ef`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x1800a58ef`
- `SHCORE!__imp_IStream_WriteStrLong` at `0x1800a5888`
- `SHCORE!__imp_IStream_WriteStrLong` at `0x1800a5888`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CContentSnippetBuilder::BuildContentSnippetProperty(
        CContentSnippetBuilder *this,
        struct tagPROPVARIANT *a2)
{
  IStream *v4; // rbx
  int inited; // edi
  unsigned int v6; // esi
  __int64 v7; // r14
  unsigned int pv; // [rsp+60h] [rbp+18h] BYREF
  IStream *v10; // [rsp+68h] [rbp+20h] BYREF

  v10 = 0;
  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  Microsoft::WRL::ComPtr<IStream>::InternalRelease(&v10);
  v10 = SHCreateMemStream(0, 0);
  v4 = v10;
  if ( v10 )
  {
    pv = *((_DWORD *)this + 14);
    inited = IStream_Write(v10, &pv, 4u);
    if ( inited >= 0 )
    {
      inited = IStream_WriteStrLong(v4, *((_QWORD *)this + 2));
      if ( inited >= 0 )
      {
        v6 = 0;
        while ( v6 < pv )
        {
          v7 = 32LL * v6;
          inited = IStream_Write(v4, (const void *)(v7 + *((_QWORD *)this + 6)), 4u);
          if ( inited >= 0 )
          {
            inited = IStream_Write(v4, (const void *)(v7 + *((_QWORD *)this + 6) + 4LL), 4u);
            if ( inited >= 0 )
              inited = IStream_WriteStr(v4, *(PCWSTR *)(v7 + *((_QWORD *)this + 6) + 8));
          }
          ++v6;
          if ( inited < 0 )
            goto LABEL_14;
        }
        inited = IStream_Reset(v4);
        if ( inited >= 0 )
          inited = InitPropVariantFromStreamAsBlob((__int64 *)v4, (__int64)a2);
      }
    }
  }
  else
  {
    inited = -2147024882;
  }
LABEL_14:
  Microsoft::WRL::ComPtr<IStream>::InternalRelease(&v10);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800a5810  mov     [rsp+arg_0], rbx
0x1800a5815  push    rbp
0x1800a5816  push    rsi
0x1800a5817  push    rdi
0x1800a5818  push    r14
0x1800a581a  push    r15
0x1800a581c  sub     rsp, 20h
0x1800a5820  xor     eax, eax
0x1800a5822  xorps   xmm0, xmm0
0x1800a5825  mov     rbp, rcx
0x1800a5828  mov     [rsp+48h+arg_18], rax
0x1800a582d  movups  xmmword ptr [rdx], xmm0
0x1800a5830  lea     rcx, [rsp+48h+arg_18]
0x1800a5835  mov     [rdx+10h], rax
0x1800a5839  mov     r15, rdx
0x1800a583c  call    ?InternalRelease@?$ComPtr@UIStream@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IStream>::InternalRelease(void)
0x1800a5841  xor     edx, edx; cbInit
0x1800a5843  xor     ecx, ecx; pInit
0x1800a5845  call    cs:__imp_SHCreateMemStream
0x1800a584b  mov     [rsp+48h+arg_18], rax
0x1800a5850  mov     rbx, rax
0x1800a5853  test    rax, rax
0x1800a5856  jz      loc_1800A591A
0x1800a585c  mov     eax, [rbp+38h]
0x1800a585f  lea     rdx, [rsp+48h+pv]; pv
0x1800a5864  mov     r8d, 4; cb
0x1800a586a  mov     [rsp+48h+pv], eax
0x1800a586e  mov     rcx, rbx; pstm
0x1800a5871  call    cs:__imp_IStream_Write
0x1800a5877  mov     edi, eax
0x1800a5879  test    eax, eax
0x1800a587b  js      loc_1800A591F
0x1800a5881  mov     rdx, [rbp+10h]
0x1800a5885  mov     rcx, rbx
0x1800a5888  call    cs:__imp_IStream_WriteStrLong
0x1800a588e  mov     edi, eax
0x1800a5890  test    eax, eax
0x1800a5892  js      loc_1800A591F
0x1800a5898  xor     esi, esi
0x1800a589a  mov     rcx, rbx; pstm
0x1800a589d  cmp     esi, [rsp+48h+pv]
0x1800a58a1  jnb     short loc_1800A58FF
0x1800a58a3  mov     rdx, [rbp+30h]
0x1800a58a7  mov     r8d, 4; cb
0x1800a58ad  mov     r14d, esi
0x1800a58b0  shl     r14, 5
0x1800a58b4  add     rdx, r14; pv
0x1800a58b7  call    cs:__imp_IStream_Write
0x1800a58bd  mov     edi, eax
0x1800a58bf  test    eax, eax
0x1800a58c1  js      short loc_1800A58F7
0x1800a58c3  mov     rdx, [rbp+30h]
0x1800a58c7  mov     r8d, 4; cb
0x1800a58cd  add     rdx, 4
0x1800a58d1  mov     rcx, rbx; pstm
0x1800a58d4  add     rdx, r14; pv
0x1800a58d7  call    cs:__imp_IStream_Write
0x1800a58dd  mov     edi, eax
0x1800a58df  test    eax, eax
0x1800a58e1  js      short loc_1800A58F7
0x1800a58e3  mov     rdx, [rbp+30h]
0x1800a58e7  mov     rcx, rbx; pstm
0x1800a58ea  mov     rdx, [r14+rdx+8]; psz
0x1800a58ef  call    cs:__imp_IStream_WriteStr
0x1800a58f5  mov     edi, eax
0x1800a58f7  inc     esi
0x1800a58f9  test    edi, edi
0x1800a58fb  jns     short loc_1800A589A
0x1800a58fd  jmp     short loc_1800A591F
0x1800a58ff  call    cs:__imp_IStream_Reset
0x1800a5905  mov     edi, eax
0x1800a5907  test    eax, eax
0x1800a5909  js      short loc_1800A591F
0x1800a590b  mov     rdx, r15
0x1800a590e  mov     rcx, rbx
0x1800a5911  call    InitPropVariantFromStreamAsBlob
0x1800a5916  mov     edi, eax
0x1800a5918  jmp     short loc_1800A591F
0x1800a591a  mov     edi, 8007000Eh
0x1800a591f  lea     rcx, [rsp+48h+arg_18]
0x1800a5924  call    ?InternalRelease@?$ComPtr@UIStream@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IStream>::InternalRelease(void)
0x1800a5929  mov     rbx, [rsp+48h+arg_0]
0x1800a592e  mov     eax, edi
0x1800a5930  add     rsp, 20h
0x1800a5934  pop     r15
0x1800a5936  pop     r14
0x1800a5938  pop     rdi
0x1800a5939  pop     rsi
0x1800a593a  pop     rbp
0x1800a593b  retn
```
