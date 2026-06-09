# DfsRootFolder::DfsRootFolder(ushort const *,ushort const *,ushort const *,uchar,ushort const *,DfsObjectTypeEnumeration,ulong *)

- ea: `0x140026fdc`
- end: `0x140027305`
- name: `??0DfsRootFolder@@QEAA@PEBG00E0W4DfsObjectTypeEnumeration@@PEAK@Z`
- size: `809`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x140009b94`
- `0x140020720`
- `0x14004439c`

## callees

- `0x1400011d0`
- `0x140026ec8`
- `0x140026fdc`
- `0x140029e7c`
- `0x1400586a8`
- `0x140058d7c`
- `0x14005ab08`
- `0x14005b1b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027221`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400270e4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400270f7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400270e4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400270f7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140027209`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140027209`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1400271ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1400271ec`

## pseudocode

```c
__int64 __fastcall DfsRootFolder::DfsRootFolder(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        char a5,
        __int64 a6,
        unsigned int a7,
        unsigned int *a8)
{
  unsigned int UnicodeStringFromString; // edx
  char *v11; // rax
  char *v12; // rbx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v15; // rcx
  __int64 result; // rax

  DfsFolder::DfsFolder(a1, 0, a7);
  *(_QWORD *)a1 = &DfsRootFolder::`vftable';
  DfsRtlInitUnicodeStringEx(a1 + 136, 0);
  DfsRtlInitUnicodeStringEx(a1 + 280, 0);
  DfsRtlInitUnicodeStringEx(a1 + 296, 0);
  DfsRtlInitUnicodeStringEx(a1 + 200, 0);
  DfsRtlInitUnicodeStringEx(a1 + 152, 0);
  DfsRtlInitUnicodeStringEx(a1 + 168, 0);
  DfsRtlInitUnicodeStringEx(a1 + 184, 0);
  DfsRtlInitUnicodeStringEx(a1 + 432, 0);
  *(_WORD *)(a1 + 217) = 1;
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 456) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 480) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  *(_DWORD *)(a1 + 272) = 0;
  *(_WORD *)(a1 + 124) = 0;
  *(_DWORD *)(a1 + 312) = 0;
  InitializeSRWLock((PSRWLOCK)(a1 + 112));
  InitializeSRWLock((PSRWLOCK)(a1 + 264));
  *(_DWORD *)(a1 + 120) = 0;
  *(_DWORD *)(a1 + 128) = 0;
  *(_BYTE *)(a1 + 451) = 0;
  UnicodeStringFromString = DfsCreateUnicodeStringFromString(a1 + 200, a6);
  if ( !UnicodeStringFromString )
  {
    UnicodeStringFromString = DfsCreateUnicodeStringFromString(a1 + 296, a3);
    if ( !UnicodeStringFromString )
    {
      UnicodeStringFromString = DfsCreateUnicodeStringFromString(a1 + 152, a4);
      if ( !UnicodeStringFromString )
      {
        *(_BYTE *)(a1 + 216) = a5;
        if ( !a5
          || (UnicodeStringFromString = DfspSaveNameContext(
                                          a2,
                                          (struct _UNICODE_STRING *)(a1 + 136),
                                          (struct _UNICODE_STRING *)(a1 + 280))) == 0 )
        {
          *(_QWORD *)(a1 + 488) = 0;
          v11 = (char *)operator new(0x78u);
          v12 = v11;
          if ( !v11 )
          {
            *(_QWORD *)(a1 + 480) = 0;
            UnicodeStringFromString = 8;
            goto LABEL_13;
          }
          *((_DWORD *)v11 + 7) = -1;
          *((_DWORD *)v11 + 3) = 1635013444;
          *((_DWORD *)v11 + 2) = 1;
          *(_QWORD *)v11 = &DfsSiteSupport::`vftable';
          *((_QWORD *)v11 + 2) = 0;
          *((_DWORD *)v11 + 6) = 0;
          *((_QWORD *)v11 + 4) = 0;
          *((_QWORD *)v11 + 5) = 0;
          *((_QWORD *)v11 + 6) = 0;
          *((_QWORD *)v11 + 7) = 0;
          *((_QWORD *)v11 + 8) = 0;
          *((_QWORD *)v11 + 9) = 0;
          *(_QWORD *)(v11 + 84) = 0;
          *(_QWORD *)(v11 + 92) = 0;
          GetLocalTime((LPSYSTEMTIME)(v11 + 100));
          *(_QWORD *)(a1 + 480) = v12;
          EventW = CreateEventW(0, 1, 0, 0);
          *(_QWORD *)(a1 + 400) = EventW;
          if ( EventW )
          {
            *(_QWORD *)(a1 + 320) = 0;
            *(_DWORD *)(a1 + 328) = 3;
            *(_QWORD *)(a1 + 336) = 0;
            *(_QWORD *)(a1 + 344) = 0;
            *(_QWORD *)(a1 + 352) = 0;
            *(_QWORD *)(a1 + 360) = 0;
            *(_QWORD *)(a1 + 368) = 0;
            *(_QWORD *)(a1 + 376) = 0;
            *(_DWORD *)(a1 + 384) = 0;
            *(_DWORD *)(a1 + 388) = 1;
            *(_DWORD *)(a1 + 392) = 72;
            *(_QWORD *)(a1 + 336) = *Block;
            *(_DWORD *)(a1 + 52) = 4096;
            UnicodeStringFromString = DfsInitializePrefixTable(a1 + 256);
            if ( UnicodeStringFromString )
              goto LABEL_13;
            LastError = DfsInitializeNameTable(v15, a1 + 456);
          }
          else
          {
            LastError = GetLastError();
          }
          UnicodeStringFromString = LastError;
        }
      }
    }
  }
LABEL_13:
  *(_WORD *)(a1 + 448) = 0;
  *(_QWORD *)(a1 + 472) = 0;
  *a8 = UnicodeStringFromString;
  result = a1;
  *(_QWORD *)(a1 + 464) = 0;
  return result;
}

```

## disassembly

```asm
0x140026fdc  mov     [rsp+arg_0], rbx
0x140026fe1  mov     [rsp+arg_18], r9
0x140026fe6  mov     [rsp+arg_8], rdx
0x140026feb  push    rbp
0x140026fec  push    rsi
0x140026fed  push    rdi
0x140026fee  push    r12
0x140026ff0  push    r13
0x140026ff2  push    r14
0x140026ff4  push    r15
0x140026ff6  sub     rsp, 20h
0x140026ffa  mov     r13, r8
0x140026ffd  xor     edx, edx
0x140026fff  mov     r8d, [rsp+58h+arg_30]
0x140027007  mov     rdi, rcx
0x14002700a  call    ??0DfsFolder@@QEAA@PEAV0@W4DfsObjectTypeEnumeration@@@Z; DfsFolder::DfsFolder(DfsFolder *,DfsObjectTypeEnumeration)
0x14002700f  lea     rax, ??_7DfsRootFolder@@6B@; const DfsRootFolder::`vftable'
0x140027016  xor     edx, edx
0x140027018  lea     r15, [rdi+88h]
0x14002701f  mov     [rdi], rax
0x140027022  mov     rcx, r15
0x140027025  call    DfsRtlInitUnicodeStringEx
0x14002702a  lea     r12, [rdi+118h]
0x140027031  xor     edx, edx
0x140027033  mov     rcx, r12
0x140027036  call    DfsRtlInitUnicodeStringEx
0x14002703b  lea     rsi, [rdi+128h]
0x140027042  xor     edx, edx
0x140027044  mov     rcx, rsi
0x140027047  call    DfsRtlInitUnicodeStringEx
0x14002704c  lea     rbx, [rdi+0C8h]
0x140027053  xor     edx, edx
0x140027055  mov     rcx, rbx
0x140027058  call    DfsRtlInitUnicodeStringEx
0x14002705d  lea     rbp, [rdi+98h]
0x140027064  xor     edx, edx
0x140027066  mov     rcx, rbp
0x140027069  call    DfsRtlInitUnicodeStringEx
0x14002706e  lea     rcx, [rdi+0A8h]
0x140027075  xor     edx, edx
0x140027077  call    DfsRtlInitUnicodeStringEx
0x14002707c  lea     rcx, [rdi+0B8h]
0x140027083  xor     edx, edx
0x140027085  call    DfsRtlInitUnicodeStringEx
0x14002708a  lea     rcx, [rdi+1B0h]
0x140027091  xor     edx, edx
0x140027093  call    DfsRtlInitUnicodeStringEx
0x140027098  xor     ecx, ecx
0x14002709a  mov     word ptr [rdi+0D9h], 1
0x1400270a3  mov     [rdi+0E8h], rcx
0x1400270aa  lea     r14, [rdi+1C8h]
0x1400270b1  mov     [rdi+0F0h], rcx
0x1400270b8  mov     [r14], rcx
0x1400270bb  mov     [rdi+100h], rcx
0x1400270c2  mov     [rdi+1E0h], rcx
0x1400270c9  mov     [rdi+0F8h], rcx
0x1400270d0  mov     [rdi+110h], ecx
0x1400270d6  mov     [rdi+7Ch], cx
0x1400270da  mov     [rdi+138h], ecx
0x1400270e0  lea     rcx, [rdi+70h]; SRWLock
0x1400270e4  call    cs:__imp_InitializeSRWLock
0x1400270eb  nop     dword ptr [rax+rax+00h]
0x1400270f0  lea     rcx, [rdi+108h]; SRWLock
0x1400270f7  call    cs:__imp_InitializeSRWLock
0x1400270fe  nop     dword ptr [rax+rax+00h]
0x140027103  mov     rdx, [rsp+58h+arg_28]
0x14002710b  xor     eax, eax
0x14002710d  mov     rcx, rbx
0x140027110  mov     [rdi+78h], eax
0x140027113  mov     [rdi+80h], eax
0x140027119  mov     [rdi+1C3h], al
0x14002711f  call    DfsCreateUnicodeStringFromString
0x140027124  mov     edx, eax
0x140027126  test    eax, eax
0x140027128  jnz     loc_1400272CA
0x14002712e  mov     rdx, r13
0x140027131  mov     rcx, rsi
0x140027134  call    DfsCreateUnicodeStringFromString
0x140027139  xor     esi, esi
0x14002713b  mov     edx, eax
0x14002713d  test    eax, eax
0x14002713f  jnz     loc_1400272CC
0x140027145  mov     rdx, [rsp+58h+arg_18]
0x14002714a  mov     rcx, rbp
0x14002714d  call    DfsCreateUnicodeStringFromString
0x140027152  mov     edx, eax
0x140027154  test    eax, eax
0x140027156  jnz     loc_1400272CC
0x14002715c  mov     al, [rsp+58h+arg_20]
0x140027163  mov     [rdi+0D8h], al
0x140027169  test    al, al
0x14002716b  jz      short loc_140027187
0x14002716d  mov     rcx, [rsp+58h+arg_8]; unsigned __int16 *
0x140027172  mov     r8, r12; struct _UNICODE_STRING *
0x140027175  mov     rdx, r15; struct _UNICODE_STRING *
0x140027178  call    ?DfspSaveNameContext@@YAKPEBGPEAU_UNICODE_STRING@@1@Z; DfspSaveNameContext(ushort const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14002717d  mov     edx, eax
0x14002717f  test    eax, eax
0x140027181  jnz     loc_1400272CC
0x140027187  mov     ecx, 78h ; 'x'; Size
0x14002718c  mov     [rdi+1E8h], rsi
0x140027193  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140027198  mov     rbx, rax
0x14002719b  test    rax, rax
0x14002719e  jz      loc_1400272BC
0x1400271a4  or      dword ptr [rbx+1Ch], 0FFFFFFFFh
0x1400271a8  lea     rcx, [rbx+64h]; lpSystemTime
0x1400271ac  mov     dword ptr [rax+0Ch], 61745344h
0x1400271b3  mov     ebp, 1
0x1400271b8  mov     [rax+8], ebp
0x1400271bb  lea     rax, ??_7DfsSiteSupport@@6B@; const DfsSiteSupport::`vftable'
0x1400271c2  mov     [rbx], rax
0x1400271c5  mov     [rbx+10h], rsi
0x1400271c9  mov     [rbx+18h], esi
0x1400271cc  mov     [rbx+20h], rsi
0x1400271d0  mov     [rbx+28h], rsi
0x1400271d4  mov     [rbx+30h], rsi
0x1400271d8  mov     [rbx+38h], rsi
0x1400271dc  mov     [rbx+40h], rsi
0x1400271e0  mov     [rbx+48h], rsi
0x1400271e4  mov     [rbx+54h], rsi
0x1400271e8  mov     [rbx+5Ch], rsi
0x1400271ec  call    cs:__imp_GetLocalTime
0x1400271f3  nop     dword ptr [rax+rax+00h]
0x1400271f8  xor     r9d, r9d; lpName
0x1400271fb  mov     [rdi+1E0h], rbx
0x140027202  xor     r8d, r8d; bInitialState
0x140027205  mov     edx, ebp; bManualReset
0x140027207  xor     ecx, ecx; lpEventAttributes
0x140027209  call    cs:__imp_CreateEventW
0x140027210  nop     dword ptr [rax+rax+00h]
0x140027215  mov     [rdi+190h], rax
0x14002721c  test    rax, rax
0x14002721f  jnz     short loc_140027234
0x140027221  call    cs:__imp_GetLastError
0x140027228  nop     dword ptr [rax+rax+00h]
0x14002722d  mov     edx, eax
0x14002722f  jmp     loc_1400272CC
0x140027234  mov     [rdi+140h], rsi
0x14002723b  lea     rcx, [rdi+100h]
0x140027242  mov     dword ptr [rdi+148h], 3
0x14002724c  mov     [rdi+150h], rsi
0x140027253  mov     [rdi+158h], rsi
0x14002725a  mov     [rdi+160h], rsi
0x140027261  mov     [rdi+168h], rsi
0x140027268  mov     [rdi+170h], rsi
0x14002726f  mov     [rdi+178h], rsi
0x140027276  mov     [rdi+180h], esi
0x14002727c  mov     [rdi+184h], ebp
0x140027282  mov     dword ptr [rdi+188h], 48h ; 'H'
0x14002728c  mov     rax, cs:Block
0x140027293  mov     r8, [rax]
0x140027296  mov     [rdi+150h], r8
0x14002729d  mov     dword ptr [rdi+34h], 1000h
0x1400272a4  call    DfsInitializePrefixTable
0x1400272a9  mov     edx, eax
0x1400272ab  test    eax, eax
0x1400272ad  jnz     short loc_1400272CC
0x1400272af  mov     rdx, r14
0x1400272b2  call    DfsInitializeNameTable
0x1400272b7  jmp     loc_14002722D
0x1400272bc  mov     [rdi+1E0h], rsi
0x1400272c3  mov     edx, 8
0x1400272c8  jmp     short loc_1400272CC
0x1400272ca  xor     esi, esi
0x1400272cc  mov     rax, [rsp+58h+arg_38]
0x1400272d4  and     word ptr [rdi+1C0h], 0
0x1400272dc  mov     rbx, [rsp+58h+arg_0]
0x1400272e1  mov     [rdi+1D8h], rsi
0x1400272e8  mov     [rax], edx
0x1400272ea  mov     rax, rdi
0x1400272ed  mov     [rdi+1D0h], rsi
0x1400272f4  add     rsp, 20h
0x1400272f8  pop     r15
0x1400272fa  pop     r14
0x1400272fc  pop     r13
0x1400272fe  pop     r12
0x140027300  pop     rdi
0x140027301  pop     rsi
0x140027302  pop     rbp
0x140027303  retn
```
