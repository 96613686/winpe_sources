# CDirectMusicPortDownload::GetBufferInternal(ulong,IDirectMusicDownload * *)

- ea: `0x180010184`
- end: `0x180010226`
- name: `?GetBufferInternal@CDirectMusicPortDownload@@AEAAJKPEAPEAUIDirectMusicDownload@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(CDirectMusicPortDownload *__hidden this, unsigned int, struct IDirectMusicDownload **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f6a4`
- `0x180010160`
- `0x180017fb4`
- `0x180018324`

## callees

- `0x180010184`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010209`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010209`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800101a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800101a1`

## pseudocode

```c
__int64 __fastcall CDirectMusicPortDownload::GetBufferInternal(
        CDirectMusicPortDownload *this,
        unsigned int a2,
        struct IDirectMusicDownload **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  char v7; // di
  __int64 v8; // rcx
  __int64 v9; // rdx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 272);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  v7 = 0;
  v8 = *((_QWORD *)this + a2 % 0x1F + 3);
  v9 = (v8 - 16) & -(__int64)(v8 != 0);
  if ( v9 )
  {
    while ( a2 != *(_DWORD *)(v9 + 32) )
    {
      v9 = (*(_QWORD *)(v9 + 16) - 16LL) & ((unsigned __int128)-(__int128)*(unsigned __int64 *)(v9 + 16) >> 64);
      if ( !v9 )
        goto LABEL_6;
    }
    *a3 = (struct IDirectMusicDownload *)v9;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    v7 = 1;
  }
LABEL_6:
  LeaveCriticalSection(v3);
  return v7 == 0 ? 0x88781120 : 0;
}

```

## disassembly

```asm
0x180010184  push    rbx
0x180010186  push    rbp
0x180010187  push    rsi
0x180010188  push    rdi
0x180010189  push    r14
0x18001018b  sub     rsp, 20h
0x18001018f  lea     rbp, [rcx+110h]
0x180010196  mov     rbx, rcx
0x180010199  mov     rcx, rbp; lpCriticalSection
0x18001019c  mov     r14, r8
0x18001019f  mov     esi, edx
0x1800101a1  call    cs:__imp_EnterCriticalSection
0x1800101a7  mov     eax, 8421085h
0x1800101ac  mov     ecx, esi
0x1800101ae  mul     esi
0x1800101b0  mov     eax, esi
0x1800101b2  xor     dil, dil
0x1800101b5  sub     eax, edx
0x1800101b7  shr     eax, 1
0x1800101b9  add     eax, edx
0x1800101bb  shr     eax, 4
0x1800101be  imul    eax, 1Fh
0x1800101c1  sub     ecx, eax
0x1800101c3  mov     rcx, [rbx+rcx*8+18h]
0x1800101c8  lea     rax, [rcx-10h]
0x1800101cc  neg     rcx
0x1800101cf  sbb     rdx, rdx
0x1800101d2  and     rdx, rax
0x1800101d5  jz      short loc_180010206
0x1800101d7  cmp     esi, [rdx+20h]
0x1800101da  jz      short loc_1800101F1
0x1800101dc  mov     rax, [rdx+10h]
0x1800101e0  lea     rcx, [rax-10h]
0x1800101e4  neg     rax
0x1800101e7  sbb     rdx, rdx
0x1800101ea  and     rdx, rcx
0x1800101ed  jnz     short loc_1800101D7
0x1800101ef  jmp     short loc_180010206
0x1800101f1  mov     [r14], rdx
0x1800101f4  mov     rcx, rdx
0x1800101f7  mov     rax, [rdx]
0x1800101fa  mov     rax, [rax+8]
0x1800101fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010203  mov     dil, 1
0x180010206  mov     rcx, rbp; lpCriticalSection
0x180010209  call    cs:__imp_LeaveCriticalSection
0x18001020f  neg     dil
0x180010212  sbb     eax, eax
0x180010214  not     eax
0x180010216  and     eax, 88781120h
0x18001021b  add     rsp, 20h
0x18001021f  pop     r14
0x180010221  pop     rdi
0x180010222  pop     rsi
0x180010223  pop     rbp
0x180010224  pop     rbx
0x180010225  retn
```
