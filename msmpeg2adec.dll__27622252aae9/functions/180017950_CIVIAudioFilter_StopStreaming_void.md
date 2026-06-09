# CIVIAudioFilter::StopStreaming(void)

- ea: `0x180017950`
- end: `0x180017b0f`
- name: `?StopStreaming@CIVIAudioFilter@@MEAAJXZ`
- size: `447`
- prototype: `__int64 __fastcall(CIVIAudioFilter *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013a40`
- `0x180017950`
- `0x18001cdc0`
- `0x180033bf0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017a3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017a3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800179df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017add`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017aed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800179df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017add`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017aed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017974`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017990`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800179ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017974`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017990`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800179ad`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800179cf`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800179cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CIVIAudioFilter::StopStreaming(CIVIAudioFilter *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  struct _RTL_CRITICAL_SECTION *v3; // r14
  __int64 v4; // rcx
  _DWORD *v5; // rcx
  unsigned int v6; // ebx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 176);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  if ( this != (CIVIAudioFilter *)-256LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
    if ( !*((_DWORD *)this + 64) )
      EventWrite(*((_QWORD *)this + 33), &MSMPEG2ADEC_PLAYBACK_STOP, 0, 0);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  }
  v4 = *((_QWORD *)this + 2073);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 2073) = 0;
  }
  *((_QWORD *)this + 2076) = 0;
  *((_QWORD *)this + 2079) = 0;
  *((_QWORD *)this + 72) = 0;
  *((_DWORD *)this + 4289) = 0;
  *((_DWORD *)this + 1542) = 0;
  if ( *((_DWORD *)this + 128) )
    CoTaskMemFree(*((LPVOID *)this + 65));
  *(_OWORD *)((char *)this + 440) = 0;
  *(_OWORD *)((char *)this + 456) = 0;
  *(_OWORD *)((char *)this + 472) = 0;
  *(_OWORD *)((char *)this + 488) = 0;
  *(_OWORD *)((char *)this + 504) = 0;
  *((_QWORD *)this + 65) = 0;
  *((_DWORD *)this + 120) = 1;
  *((_DWORD *)this + 118) = 1;
  v5 = (_DWORD *)((char *)this + 248);
  if ( *((_DWORD *)this + 1476) || *v5 )
  {
    *((_DWORD *)this + 1476) = 0;
    if ( *v5 )
      --*v5;
  }
  if ( *((_QWORD *)this + 830) )
    AACAudioDecoderClose((char *)this + 6640);
  AudioRateChange::Reset((CIVIAudioFilter *)((char *)this + 15472));
  v6 = CIVIAudioCodec::ResetAudioDecoder((CIVIAudioFilter *)((char *)this + 232));
  LeaveCriticalSection(v3);
  LeaveCriticalSection(v2);
  return v6;
}

```

## disassembly

```asm
0x180017950  mov     [rsp+arg_10], rbx
0x180017955  mov     [rsp+arg_18], rbp
0x18001795a  push    rsi
0x18001795b  push    rdi
0x18001795c  push    r14
0x18001795e  sub     rsp, 20h
0x180017962  mov     rbx, rcx
0x180017965  lea     rbp, [rcx+88h]
0x18001796c  mov     [rsp+38h+arg_0], rbp
0x180017971  mov     rcx, rbp; lpCriticalSection
0x180017974  call    cs:__imp_EnterCriticalSection
0x18001797b  nop     dword ptr [rax+rax+00h]
0x180017980  nop
0x180017981  lea     r14, [rbx+0B0h]
0x180017988  mov     [rsp+38h+arg_8], r14
0x18001798d  mov     rcx, r14; lpCriticalSection
0x180017990  call    cs:__imp_EnterCriticalSection
0x180017997  nop     dword ptr [rax+rax+00h]
0x18001799c  nop
0x18001799d  lea     rdi, [rbx+100h]
0x1800179a4  test    rdi, rdi
0x1800179a7  jz      short loc_1800179EB
0x1800179a9  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800179ad  call    cs:__imp_EnterCriticalSection
0x1800179b4  nop     dword ptr [rax+rax+00h]
0x1800179b9  cmp     dword ptr [rdi], 0
0x1800179bc  jnz     short loc_1800179DB
0x1800179be  xor     r9d, r9d; UserData
0x1800179c1  xor     r8d, r8d; UserDataCount
0x1800179c4  lea     rdx, MSMPEG2ADEC_PLAYBACK_STOP; EventDescriptor
0x1800179cb  mov     rcx, [rdi+8]; RegHandle
0x1800179cf  call    cs:__imp_EventWrite
0x1800179d6  nop     dword ptr [rax+rax+00h]
0x1800179db  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800179df  call    cs:__imp_LeaveCriticalSection
0x1800179e6  nop     dword ptr [rax+rax+00h]
0x1800179eb  mov     rcx, [rbx+40C8h]
0x1800179f2  xor     esi, esi
0x1800179f4  test    rcx, rcx
0x1800179f7  jz      short loc_180017A0D
0x1800179f9  mov     rax, [rcx]
0x1800179fc  mov     rax, [rax+10h]
0x180017a00  call    cs:__guard_dispatch_icall_fptr
0x180017a06  mov     [rbx+40C8h], rsi
0x180017a0d  mov     [rbx+40E0h], rsi
0x180017a14  mov     [rbx+40F8h], rsi
0x180017a1b  mov     [rbx+240h], rsi
0x180017a22  mov     [rbx+4304h], esi
0x180017a28  mov     [rbx+1818h], esi
0x180017a2e  cmp     [rbx+200h], esi
0x180017a34  jz      short loc_180017A49
0x180017a36  mov     rcx, [rbx+208h]; pv
0x180017a3d  call    cs:__imp_CoTaskMemFree
0x180017a44  nop     dword ptr [rax+rax+00h]
0x180017a49  xorps   xmm0, xmm0
0x180017a4c  xor     eax, eax
0x180017a4e  movups  xmmword ptr [rbx+1B8h], xmm0
0x180017a55  movups  xmmword ptr [rbx+1C8h], xmm0
0x180017a5c  movups  xmmword ptr [rbx+1D8h], xmm0
0x180017a63  movups  xmmword ptr [rbx+1E8h], xmm0
0x180017a6a  movups  xmmword ptr [rbx+1F8h], xmm0
0x180017a71  mov     [rbx+208h], rax
0x180017a78  mov     dword ptr [rbx+1E0h], 1
0x180017a82  mov     dword ptr [rbx+1D8h], 1
0x180017a8c  lea     rcx, [rbx+0F8h]
0x180017a93  cmp     [rbx+1710h], eax
0x180017a99  jnz     short loc_180017A9F
0x180017a9b  cmp     [rcx], eax
0x180017a9d  jz      short loc_180017AAF
0x180017a9f  mov     [rbx+1710h], esi
0x180017aa5  mov     eax, [rcx]
0x180017aa7  test    eax, eax
0x180017aa9  jz      short loc_180017AAF
0x180017aab  dec     eax
0x180017aad  mov     [rcx], eax
0x180017aaf  lea     rcx, [rbx+19F0h]
0x180017ab6  cmp     [rcx], rsi
0x180017ab9  jz      short loc_180017AC0
0x180017abb  call    AACAudioDecoderClose
0x180017ac0  lea     rcx, [rbx+3C70h]; this
0x180017ac7  call    ?Reset@AudioRateChange@@QEAAXXZ; AudioRateChange::Reset(void)
0x180017acc  lea     rcx, [rbx+0E8h]; this
0x180017ad3  call    ?ResetAudioDecoder@CIVIAudioCodec@@IEAAJXZ; CIVIAudioCodec::ResetAudioDecoder(void)
0x180017ad8  mov     ebx, eax
0x180017ada  mov     rcx, r14; lpCriticalSection
0x180017add  call    cs:__imp_LeaveCriticalSection
0x180017ae4  nop     dword ptr [rax+rax+00h]
0x180017ae9  nop
0x180017aea  mov     rcx, rbp; lpCriticalSection
0x180017aed  call    cs:__imp_LeaveCriticalSection
0x180017af4  nop     dword ptr [rax+rax+00h]
0x180017af9  mov     eax, ebx
0x180017afb  mov     rbx, [rsp+38h+arg_10]
0x180017b00  mov     rbp, [rsp+38h+arg_18]
0x180017b05  add     rsp, 20h
0x180017b09  pop     r14
0x180017b0b  pop     rdi
0x180017b0c  pop     rsi
0x180017b0d  retn
```
