# CConnection::CConnection(void)

- ea: `0x10045e874`
- end: `0x10045ea4b`
- name: `??0CConnection@@QEAA@XZ`
- size: `471`
- prototype: `CConnection *__fastcall(CConnection *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10045ff60`

## callees

- `0x10045e874`
- `0x100546894`
- `0x100548140`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x10045e8aa`
- `KERNEL32!InitializeSListHead` at `0x10045e8aa`
- `KERNEL32!CreateEventW` at `0x10045e9bd`
- `KERNEL32!CreateEventW` at `0x10045e9e8`
- `KERNEL32!CreateEventW` at `0x10045e9bd`
- `KERNEL32!CreateEventW` at `0x10045e9e8`
- `KERNEL32!GetLastError` at `0x10045e9cf`
- `KERNEL32!GetLastError` at `0x10045e9fa`
- `KERNEL32!GetLastError` at `0x10045e9cf`
- `KERNEL32!GetLastError` at `0x10045e9fa`

## pseudocode

```c
CConnection *__fastcall CConnection::CConnection(CConnection *this)
{
  HANDLE EventW; // rax
  HANDLE v3; // rax

  *((_QWORD *)this + 4) = 4096;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &CConnection::`vftable';
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 5) = 0;
  InitializeSListHead((PSLIST_HEADER)this + 3);
  *((_WORD *)this + 32) = 5;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_DWORD *)this + 94) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_DWORD *)this + 98) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 1;
  *((_DWORD *)this + 104) = 0;
  *((_WORD *)this + 210) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_WORD *)this + 220) = 0;
  *((_BYTE *)this + 442) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_DWORD *)this + 114) = 0;
  *((_DWORD *)this + 123) = 0;
  *((_DWORD *)this + 968) = 0;
  *((_WORD *)this + 1938) = 0;
  *(_DWORD *)((char *)this + 3878) = 0;
  *((_QWORD *)this + 486) = 0;
  memset_0((char *)this + 3896, 0, 0x88u);
  *((_QWORD *)this + 508) = 0;
  *((_QWORD *)this + 510) = 0;
  *((_QWORD *)this + 511) = 0;
  *((_QWORD *)this + 512) = 0;
  *((_QWORD *)this + 513) = 0;
  *((_BYTE *)this + 4672) = 0;
  *((_BYTE *)this + 4673) = 0;
  *((_QWORD *)this + 585) = 0;
  *((_DWORD *)this + 1172) = 0;
  *((_DWORD *)this + 1173) = 0;
  *((_WORD *)this + 1538) = 0;
  *((_WORD *)this + 1807) = 0;
  *((_BYTE *)this + 104) = 0;
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)this + 511) = EventW;
  if ( EventW )
    *((_QWORD *)this + 510) = 0;
  else
    GetLastError();
  v3 = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)this + 513) = v3;
  if ( v3 )
    *((_QWORD *)this + 512) = 0;
  else
    GetLastError();
  *((_DWORD *)this + 1160) = 0;
  *((_OWORD *)this + 252) = 0;
  *((_OWORD *)this + 253) = 0;
  *((_DWORD *)this + 1016) = bidObtainItemIDW(`CConnection::CConnection'::`4'::_bidPtrSA_051_659[0], this, 0);
  return this;
}

```

## disassembly

```asm
0x10045e874  mov     [rsp+arg_0], rbx
0x10045e879  mov     [rsp+arg_8], rsi
0x10045e87e  push    rdi
0x10045e87f  sub     rsp, 20h
0x10045e883  xor     esi, esi
0x10045e885  mov     qword ptr [rcx+20h], 1000h
0x10045e88d  lea     rax, ??_7CConnection@@6B@; const CConnection::`vftable'
0x10045e894  mov     [rcx+10h], rsi
0x10045e898  mov     [rcx], rax
0x10045e89b  mov     rdi, rcx
0x10045e89e  mov     [rcx+18h], rsi
0x10045e8a2  mov     [rcx+28h], rsi
0x10045e8a6  add     rcx, 30h ; '0'; ListHead
0x10045e8aa  call    cs:__imp_InitializeSListHead
0x10045e8b0  lea     eax, [rsi+5]
0x10045e8b3  xor     edx, edx; Val
0x10045e8b5  mov     [rdi+40h], ax
0x10045e8b9  lea     ebx, [rsi+1]
0x10045e8bc  mov     [rdi+50h], esi
0x10045e8bf  lea     rcx, [rdi+0F38h]; void *
0x10045e8c6  mov     [rdi+58h], rsi
0x10045e8ca  mov     r8d, 88h; Size
0x10045e8d0  mov     [rdi+60h], esi
0x10045e8d3  mov     [rdi+168h], rsi
0x10045e8da  mov     [rdi+170h], rsi
0x10045e8e1  mov     [rdi+178h], esi
0x10045e8e7  mov     [rdi+180h], rsi
0x10045e8ee  mov     [rdi+188h], esi
0x10045e8f4  mov     [rdi+190h], rsi
0x10045e8fb  mov     [rdi+198h], rbx
0x10045e902  mov     [rdi+1A0h], esi
0x10045e908  mov     [rdi+1A4h], si
0x10045e90f  mov     [rdi+1A8h], rsi
0x10045e916  mov     [rdi+1B0h], rsi
0x10045e91d  mov     [rdi+1B8h], si
0x10045e924  mov     [rdi+1BAh], sil
0x10045e92b  mov     [rdi+1C0h], rsi
0x10045e932  mov     [rdi+1C8h], esi
0x10045e938  mov     [rdi+1ECh], esi
0x10045e93e  mov     [rdi+0F20h], esi
0x10045e944  mov     [rdi+0F24h], si
0x10045e94b  mov     [rdi+0F26h], esi
0x10045e951  mov     [rdi+0F30h], rsi
0x10045e958  call    memset_0
0x10045e95d  mov     [rdi+0FE0h], rsi
0x10045e964  xor     r9d, r9d; lpName
0x10045e967  mov     [rdi+0FF0h], rsi
0x10045e96e  mov     r8d, ebx; bInitialState
0x10045e971  mov     [rdi+0FF8h], rsi
0x10045e978  mov     edx, ebx; bManualReset
0x10045e97a  mov     [rdi+1000h], rsi
0x10045e981  xor     ecx, ecx; lpEventAttributes
0x10045e983  mov     [rdi+1008h], rsi
0x10045e98a  mov     [rdi+1240h], sil
0x10045e991  mov     [rdi+1241h], sil
0x10045e998  mov     [rdi+1248h], rsi
0x10045e99f  mov     [rdi+1250h], esi
0x10045e9a5  mov     [rdi+1254h], esi
0x10045e9ab  mov     [rdi+0C04h], si
0x10045e9b2  mov     [rdi+0E1Eh], si
0x10045e9b9  mov     [rdi+68h], sil
0x10045e9bd  call    cs:__imp_CreateEventW
0x10045e9c3  mov     [rdi+0FF8h], rax
0x10045e9ca  test    rax, rax
0x10045e9cd  jnz     short loc_10045E9D7
0x10045e9cf  call    cs:__imp_GetLastError
0x10045e9d5  jmp     short loc_10045E9DE
0x10045e9d7  mov     [rdi+0FF0h], rsi
0x10045e9de  xor     r9d, r9d; lpName
0x10045e9e1  mov     r8d, ebx; bInitialState
0x10045e9e4  mov     edx, ebx; bManualReset
0x10045e9e6  xor     ecx, ecx; lpEventAttributes
0x10045e9e8  call    cs:__imp_CreateEventW
0x10045e9ee  mov     [rdi+1008h], rax
0x10045e9f5  test    rax, rax
0x10045e9f8  jnz     short loc_10045EA02
0x10045e9fa  call    cs:__imp_GetLastError
0x10045ea00  jmp     short loc_10045EA09
0x10045ea02  mov     [rdi+1000h], rsi
0x10045ea09  mov     [rdi+1220h], esi
0x10045ea0f  xorps   xmm0, xmm0
0x10045ea12  movups  xmmword ptr [rdi+0FC0h], xmm0
0x10045ea19  xor     r8d, r8d
0x10045ea1c  mov     rdx, rdi
0x10045ea1f  movups  xmmword ptr [rdi+0FD0h], xmm0
0x10045ea26  mov     rcx, cs:?_bidPtrSA_051_659@?3???0CConnection@@QEAA@XZ@4REBGEB; ushort const * const `CConnection::CConnection(void)'::`4'::_bidPtrSA_051_659
0x10045ea2d  call    _bidObtainItemIDW
0x10045ea32  mov     rbx, [rsp+28h+arg_0]
0x10045ea37  mov     rsi, [rsp+28h+arg_8]
0x10045ea3c  mov     [rdi+0FE0h], eax
0x10045ea42  mov     rax, rdi
0x10045ea45  add     rsp, 20h
0x10045ea49  pop     rdi
0x10045ea4a  retn
```
