# CDecodeContext::CDecodeContext(CDecodeContext::TConstructorArgs const &)

- ea: `0x180082848`
- end: `0x180082a36`
- name: `??0CDecodeContext@@QEAA@AEBUTConstructorArgs@0@@Z`
- size: `494`
- prototype: `CDecodeContext *__fastcall(CDecodeContext *__hidden this, const struct CDecodeContext::TConstructorArgs *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800826d8`

## callees

- `0x18000bad0`
- `0x18001e230`
- `0x180082848`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180082874`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180082874`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800828f8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800828f8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800828e8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800828e8`

## pseudocode

```c
CDecodeContext *__fastcall CDecodeContext::CDecodeContext(
        CDecodeContext *this,
        const struct CDecodeContext::TConstructorArgs *a2)
{
  _OWORD *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rax
  char v7; // al
  __int64 v9; // rax
  __int64 v10; // rax
  bool v11; // zf
  LARGE_INTEGER Frequency; // [rsp+30h] [rbp+8h] BYREF

  *((_QWORD *)this + 20) = *((_QWORD *)a2 + 2);
  *((_DWORD *)this + 38) = 0;
  InitializeSRWLock((PSRWLOCK)this + 1);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  CDestructionNotifier::CDestructionNotifier((CDecodeContext *)((char *)this + 32));
  *((_QWORD *)this + 21) = 0;
  *((_DWORD *)this + 45) = -1;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = (char *)this + 192;
  *((_QWORD *)this + 25) = (char *)this + 192;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_DWORD *)this + 98) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 55) = 0;
  CoCreateGuid((GUID *)((char *)this + 408));
  Frequency.QuadPart = 0;
  if ( QueryPerformanceFrequency(&Frequency) )
    *((_QWORD *)this + 55) = Frequency.QuadPart / 1000;
  std::vector<CCommandList *>::vector<CCommandList *>((char *)this + 448);
  v4 = (_OWORD *)*((_QWORD *)a2 + 5);
  *((_OWORD *)this + 13) = *v4;
  *(_OWORD *)((char *)this + 220) = *(_OWORD *)((char *)v4 + 12);
  v5 = *((_QWORD *)a2 + 6);
  *(_OWORD *)((char *)this + 236) = *(_OWORD *)v5;
  *(_OWORD *)((char *)this + 252) = *(_OWORD *)(v5 + 16);
  *(_OWORD *)((char *)this + 268) = *(_OWORD *)(v5 + 32);
  *(_OWORD *)((char *)this + 284) = *(_OWORD *)(v5 + 48);
  *(_OWORD *)((char *)this + 300) = *(_OWORD *)(v5 + 64);
  *(_OWORD *)((char *)this + 316) = *(_OWORD *)(v5 + 80);
  *((_DWORD *)this + 83) = *(_DWORD *)(v5 + 96);
  *((_QWORD *)this + 42) = 0;
  *((_DWORD *)this + 86) = 0;
  *((_WORD *)this + 180) = 0;
  v6 = *(_QWORD *)((char *)this + 236) - *(_QWORD *)&D3D11_DECODER_ENCRYPTION_HW_CENC.Data1;
  if ( !v6 )
    v6 = *(_QWORD *)((char *)this + 244) - *(_QWORD *)D3D11_DECODER_ENCRYPTION_HW_CENC.Data4;
  if ( !v6 )
    goto LABEL_6;
  v9 = *(_QWORD *)((char *)this + 236) - *(_QWORD *)&D3D11_DECODER_BITSTREAM_ENCRYPTION_TYPE_CENC.Data1;
  if ( !v9 )
    v9 = *(_QWORD *)((char *)this + 244) - *(_QWORD *)D3D11_DECODER_BITSTREAM_ENCRYPTION_TYPE_CENC.Data4;
  if ( !v9 )
    goto LABEL_6;
  v10 = *(_QWORD *)((char *)this + 236) - *(_QWORD *)&D3D11_DECODER_BITSTREAM_ENCRYPTION_TYPE_CBCS.Data1;
  if ( !v10 )
    v10 = *(_QWORD *)((char *)this + 244) - *(_QWORD *)D3D11_DECODER_BITSTREAM_ENCRYPTION_TYPE_CBCS.Data4;
  v11 = v10 == 0;
  v7 = 0;
  if ( v11 )
LABEL_6:
    v7 = 1;
  *((_BYTE *)this + 368) = v7;
  return this;
}

```

## disassembly

```asm
0x180082848  mov     [rsp+arg_8], rbx
0x18008284d  mov     [rsp+arg_10], rsi
0x180082852  push    rdi
0x180082853  sub     rsp, 20h
0x180082857  mov     rax, [rdx+10h]
0x18008285b  mov     rbx, rcx
0x18008285e  mov     [rcx+0A0h], rax
0x180082865  xor     esi, esi
0x180082867  mov     [rcx+98h], esi
0x18008286d  mov     rdi, rdx
0x180082870  add     rcx, 8; SRWLock
0x180082874  call    cs:__imp_InitializeSRWLock
0x18008287a  mov     [rbx+10h], rsi
0x18008287e  lea     rcx, [rbx+20h]; this
0x180082882  mov     [rbx+18h], rsi
0x180082886  call    ??0CDestructionNotifier@@QEAA@XZ; CDestructionNotifier::CDestructionNotifier(void)
0x18008288b  mov     [rbx+0A8h], rsi
0x180082892  lea     rax, [rbx+0C0h]
0x180082899  mov     dword ptr [rbx+0B4h], 0FFFFFFFFh
0x1800828a3  lea     rcx, [rbx+198h]; pguid
0x1800828aa  mov     [rbx+0B8h], rsi
0x1800828b1  mov     [rax], rax
0x1800828b4  mov     [rax+8], rax
0x1800828b8  mov     [rbx+178h], rsi
0x1800828bf  mov     [rbx+180h], rsi
0x1800828c6  mov     [rbx+188h], esi
0x1800828cc  mov     [rbx+190h], rsi
0x1800828d3  mov     [rbx+1A8h], rsi
0x1800828da  mov     [rbx+1B0h], rsi
0x1800828e1  mov     [rbx+1B8h], rsi
0x1800828e8  call    cs:__imp_CoCreateGuid
0x1800828ee  lea     rcx, [rsp+28h+Frequency]; lpFrequency
0x1800828f3  mov     qword ptr [rsp+28h+Frequency], rsi
0x1800828f8  call    cs:__imp_QueryPerformanceFrequency
0x1800828fe  test    eax, eax
0x180082900  jz      short loc_180082926
0x180082902  mov     rax, 20C49BA5E353F7CFh
0x18008290c  imul    qword ptr [rsp+28h+Frequency]
0x180082911  sar     rdx, 7
0x180082915  mov     rax, rdx
0x180082918  shr     rax, 3Fh
0x18008291c  add     rdx, rax
0x18008291f  mov     [rbx+1B8h], rdx
0x180082926  lea     rcx, [rbx+1C0h]; void *
0x18008292d  call    ??0?$vector@PEAVCCommandList@@V?$allocator@PEAVCCommandList@@@std@@@std@@QEAA@XZ; std::vector<CCommandList *>::vector<CCommandList *>(void)
0x180082932  mov     rcx, [rdi+28h]
0x180082936  movups  xmm0, xmmword ptr [rcx]
0x180082939  movups  xmmword ptr [rbx+0D0h], xmm0
0x180082940  movups  xmm1, xmmword ptr [rcx+0Ch]
0x180082944  movups  xmmword ptr [rbx+0DCh], xmm1
0x18008294b  mov     rax, [rdi+30h]
0x18008294f  movups  xmm0, xmmword ptr [rax]
0x180082952  movups  xmmword ptr [rbx+0ECh], xmm0
0x180082959  movups  xmm1, xmmword ptr [rax+10h]
0x18008295d  movups  xmmword ptr [rbx+0FCh], xmm1
0x180082964  movups  xmm0, xmmword ptr [rax+20h]
0x180082968  movups  xmmword ptr [rbx+10Ch], xmm0
0x18008296f  movups  xmm1, xmmword ptr [rax+30h]
0x180082973  movups  xmmword ptr [rbx+11Ch], xmm1
0x18008297a  movups  xmm0, xmmword ptr [rax+40h]
0x18008297e  movups  xmmword ptr [rbx+12Ch], xmm0
0x180082985  movups  xmm1, xmmword ptr [rax+50h]
0x180082989  movups  xmmword ptr [rbx+13Ch], xmm1
0x180082990  mov     eax, [rax+60h]
0x180082993  mov     [rbx+14Ch], eax
0x180082999  mov     [rbx+150h], rsi
0x1800829a0  mov     [rbx+158h], esi
0x1800829a6  mov     [rbx+168h], si
0x1800829ad  mov     rax, [rbx+0ECh]
0x1800829b4  sub     rax, qword ptr cs:D3D11_DECODER_ENCRYPTION_HW_CENC.Data1
0x1800829bb  jnz     short loc_1800829CB
0x1800829bd  mov     rax, [rbx+0F4h]
0x1800829c4  sub     rax, qword ptr cs:D3D11_DECODER_ENCRYPTION_HW_CENC.Data4
0x1800829cb  test    rax, rax
0x1800829ce  jnz     short loc_1800829EB
0x1800829d0  mov     al, 1
0x1800829d2  mov     rsi, [rsp+28h+arg_10]
0x1800829d7  mov     [rbx+170h], al
0x1800829dd  mov     rax, rbx
0x1800829e0  mov     rbx, [rsp+28h+arg_8]
0x1800829e5  add     rsp, 20h
0x1800829e9  pop     rdi
0x1800829ea  retn
0x1800829eb  mov     rax, [rbx+0ECh]
0x1800829f2  sub     rax, qword ptr cs:D3D11_DECODER_BITSTREAM_ENCRYPTION_TYPE_CENC.Data1
0x1800829f9  jnz     short loc_180082A09
0x1800829fb  mov     rax, [rbx+0F4h]
0x180082a02  sub     rax, qword ptr cs:D3D11_DECODER_BITSTREAM_ENCRYPTION_TYPE_CENC.Data4
0x180082a09  test    rax, rax
0x180082a0c  jz      short loc_1800829D0
0x180082a0e  mov     rax, [rbx+0ECh]
0x180082a15  sub     rax, qword ptr cs:D3D11_DECODER_BITSTREAM_ENCRYPTION_TYPE_CBCS.Data1
0x180082a1c  jnz     short loc_180082A2C
0x180082a1e  mov     rax, [rbx+0F4h]
0x180082a25  sub     rax, qword ptr cs:D3D11_DECODER_BITSTREAM_ENCRYPTION_TYPE_CBCS.Data4
0x180082a2c  test    rax, rax
0x180082a2f  mov     al, sil
0x180082a32  jnz     short loc_1800829D2
0x180082a34  jmp     short loc_1800829D0
```
