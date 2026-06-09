# NlpDeleteCacheEntry

- ea: `0x1800444e4`
- end: `0x180044781`
- name: `NlpDeleteCacheEntry`
- size: `669`
- prototype: `__int64 __fastcall(int, int, int, int, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001a470`
- `0x18003d430`

## callees

- `0x180030844`
- `0x180035ea8`
- `0x180041bb8`
- `0x180042dac`
- `0x180043968`
- `0x1800444e4`
- `0x180045d24`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044768`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044768`
- `ntdll!RtlAcquireResourceExclusive` at `0x180044530`
- `ntdll!RtlAcquireResourceExclusive` at `0x180044530`
- `ntdll!RtlReleaseResource` at `0x1800445e0`
- `ntdll!RtlReleaseResource` at `0x180044739`
- `ntdll!RtlReleaseResource` at `0x1800445e0`
- `ntdll!RtlReleaseResource` at `0x180044739`

## pseudocode

```c
__int64 __fastcall NlpDeleteCacheEntry(
        unsigned int a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        char a4,
        struct _UNICODE_STRING *a5)
{
  int v5; // ebx
  struct _UNICODE_STRING *v9; // rdi
  unsigned __int16 *v11; // rbx
  unsigned int v12; // r14d
  int v13; // eax
  int v14; // esi
  int v15; // r12d
  int v16; // eax
  size_t Size; // [rsp+30h] [rbp-28h] BYREF
  struct _LOGON_CACHE_ENTRY *v18; // [rsp+38h] [rbp-20h] BYREF
  struct _UNICODE_STRING *v19; // [rsp+40h] [rbp-18h] BYREF

  v5 = 0;
  v18 = 0;
  Size = 0;
  v9 = 0;
  v19 = 0;
  if ( !NlpCacheInitialized )
    return 0;
  RtlAcquireResourceExclusive(&NlpLogonCacheCritSec, 1u);
  if ( !HIDWORD(NlpCacheControl) )
    goto LABEL_12;
  v5 = NlpReadCacheEntry(a5, a5 + 2, a4 == 0 ? 0x10000000 : 0, (unsigned int *)&Size + 1, &v18, (unsigned int *)&Size);
  if ( v5 < 0 )
    goto LABEL_12;
  v11 = (unsigned __int16 *)v18;
  if ( a4 && *((_DWORD *)v18 + 10) >= 0x10004u && (*((_BYTE *)v18 + 140) & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_ZZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)WPP_905305d962583d6f838b30057de84013_Traceguids,
        (_DWORD)a5,
        (__int64)&a5[2]);
    v5 = -1073741730;
LABEL_12:
    RtlReleaseResource(&NlpLogonCacheCritSec);
    return (unsigned int)v5;
  }
  v12 = Size;
  v13 = NlpDeleteCacheEntryInternal(a1, a2, a3, HIDWORD(Size), Size, v18);
  v14 = v13;
  if ( a1 == -1073741710 && v13 >= 0 )
  {
    v15 = 2;
    v16 = NlpBuildAccountInfo(v11, &v19);
    v9 = v19;
    v14 = v16;
    if ( v16 >= 0 )
    {
      while ( v15 )
      {
        if ( v11 )
        {
          memset_0(v11, 0, v12);
          ((void (__fastcall *)(unsigned __int16 *))qword_180088398)(v11);
          v18 = 0;
          LODWORD(Size) = 0;
        }
        v14 = NlpReadCacheEntry(v9 + 13, v9 + 3, 0x20000000u, (unsigned int *)&Size + 1, &v18, (unsigned int *)&Size);
        if ( v14 < 0 )
        {
          v11 = (unsigned __int16 *)v18;
          v12 = Size;
          break;
        }
        --v15;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_dZZ(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            (unsigned int)WPP_905305d962583d6f838b30057de84013_Traceguids,
            HIDWORD(Size),
            (__int64)&v9[13],
            (__int64)&v9[3]);
        v11 = (unsigned __int16 *)v18;
        v12 = Size;
        v14 = NlpDeleteCacheEntryInternal(3221225586LL, a2, a3, HIDWORD(Size), Size, v18);
        if ( v14 < 0 )
          break;
      }
    }
  }
  RtlReleaseResource(&NlpLogonCacheCritSec);
  if ( v11 )
  {
    memset_0(v11, 0, v12);
    ((void (__fastcall *)(unsigned __int16 *))qword_180088398)(v11);
  }
  if ( v9 )
    LocalFree(v9);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800444e4  mov     [rsp-40h+arg_8], dx
0x1800444e9  push    rbp
0x1800444ea  push    rbx
0x1800444eb  push    rsi
0x1800444ec  push    rdi
0x1800444ed  push    r12
0x1800444ef  push    r13
0x1800444f1  push    r14
0x1800444f3  push    r15
0x1800444f5  mov     rbp, rsp
0x1800444f8  sub     rsp, 58h
0x1800444fc  xor     ebx, ebx
0x1800444fe  mov     sil, r9b
0x180044501  cmp     cs:NlpCacheInitialized, bl
0x180044507  movzx   r13d, r8w
0x18004450b  mov     r15d, ecx
0x18004450e  mov     [rbp+var_20], rbx
0x180044512  mov     dword ptr [rbp+Size], ebx
0x180044515  mov     edi, ebx
0x180044517  mov     dword ptr [rbp+Size+4], ebx
0x18004451a  mov     [rbp+var_18], rbx
0x18004451e  jnz     short loc_180044527
0x180044520  xor     eax, eax
0x180044522  jmp     loc_180044770
0x180044527  mov     dl, 1; Wait
0x180044529  lea     rcx, NlpLogonCacheCritSec; Resource
0x180044530  call    cs:__imp_RtlAcquireResourceExclusive
0x180044536  cmp     dword ptr cs:NlpCacheControl+4, ebx
0x18004453c  jz      loc_1800445D9
0x180044542  mov     r14, [rbp+arg_20]
0x180044546  lea     r9, [rbp+Size+4]; unsigned int *
0x18004454a  mov     al, sil
0x18004454d  mov     rcx, r14; struct _UNICODE_STRING *
0x180044550  neg     al
0x180044552  lea     rax, [rbp+Size]
0x180044556  sbb     r8d, r8d
0x180044559  mov     [rsp+58h+var_30], rax; unsigned int *
0x18004455e  not     r8d
0x180044561  lea     rax, [rbp+var_20]
0x180044565  lea     r12, [r14+20h]
0x180044569  mov     [rsp+58h+var_38], rax; struct _LOGON_CACHE_ENTRY **
0x18004456e  and     r8d, 10000000h; unsigned int
0x180044575  mov     rdx, r12; struct _UNICODE_STRING *
0x180044578  call    ?NlpReadCacheEntry@@YAJPEAU_UNICODE_STRING@@0KPEAKPEAPEAU_LOGON_CACHE_ENTRY@@1@Z; NlpReadCacheEntry(_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong *,_LOGON_CACHE_ENTRY * *,ulong *)
0x18004457d  mov     ebx, eax
0x18004457f  test    eax, eax
0x180044581  js      short loc_1800445D9
0x180044583  mov     rbx, [rbp+var_20]
0x180044587  test    sil, sil
0x18004458a  jz      short loc_1800445ED
0x18004458c  cmp     dword ptr [rbx+28h], 10004h
0x180044593  jb      short loc_1800445ED
0x180044595  test    byte ptr [rbx+8Ch], 1
0x18004459c  jz      short loc_1800445ED
0x18004459e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800445a5  lea     r15, WPP_GLOBAL_Control
0x1800445ac  cmp     rcx, r15
0x1800445af  jz      short loc_1800445D4
0x1800445b1  test    byte ptr [rcx+1Ch], 2
0x1800445b5  jz      short loc_1800445D4
0x1800445b7  mov     rcx, [rcx+10h]
0x1800445bb  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x1800445c2  mov     edx, 1Ah
0x1800445c7  mov     [rsp+58h+var_38], r12
0x1800445cc  mov     r9, r14
0x1800445cf  call    WPP_SF_ZZ
0x1800445d4  mov     ebx, 0C000005Eh
0x1800445d9  lea     rcx, NlpLogonCacheCritSec; Resource
0x1800445e0  call    cs:__imp_RtlReleaseResource
0x1800445e6  mov     eax, ebx
0x1800445e8  jmp     loc_180044770
0x1800445ed  mov     r14d, dword ptr [rbp+Size]
0x1800445f1  movzx   r8d, r13w
0x1800445f5  mov     r9d, dword ptr [rbp+Size+4]
0x1800445f9  mov     ecx, r15d
0x1800445fc  movzx   edx, [rbp+arg_8]
0x180044600  mov     [rsp+58h+var_30], rbx
0x180044605  mov     dword ptr [rsp+58h+var_38], r14d
0x18004460a  call    NlpDeleteCacheEntryInternal
0x18004460f  mov     esi, eax
0x180044611  cmp     r15d, 0C0000072h
0x180044618  jnz     loc_180044732
0x18004461e  test    eax, eax
0x180044620  js      loc_180044732
0x180044626  lea     rdx, [rbp+var_18]
0x18004462a  mov     rcx, rbx
0x18004462d  mov     r12d, 2
0x180044633  call    NlpBuildAccountInfo
0x180044638  mov     rdi, [rbp+var_18]
0x18004463c  mov     esi, eax
0x18004463e  test    eax, eax
0x180044640  js      loc_180044732
0x180044646  lea     r15, WPP_GLOBAL_Control
0x18004464d  test    r12d, r12d
0x180044650  jz      loc_180044732
0x180044656  test    rbx, rbx
0x180044659  jz      short loc_180044686
0x18004465b  mov     r8d, r14d; Size
0x18004465e  xor     edx, edx; Val
0x180044660  mov     rcx, rbx; void *
0x180044663  call    memset_0
0x180044668  mov     rax, cs:qword_180088398
0x18004466f  mov     rcx, rbx
0x180044672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044677  mov     [rbp+var_20], 0
0x18004467f  mov     dword ptr [rbp+Size], 0
0x180044686  lea     rax, [rbp+Size]
0x18004468a  mov     r8d, 20000000h; unsigned int
0x180044690  mov     [rsp+58h+var_30], rax; unsigned int *
0x180044695  lea     rbx, [rdi+30h]
0x180044699  lea     rax, [rbp+var_20]
0x18004469d  mov     rdx, rbx; struct _UNICODE_STRING *
0x1800446a0  lea     r14, [rdi+0D0h]
0x1800446a7  mov     [rsp+58h+var_38], rax; struct _LOGON_CACHE_ENTRY **
0x1800446ac  lea     r9, [rbp+Size+4]; unsigned int *
0x1800446b0  mov     rcx, r14; struct _UNICODE_STRING *
0x1800446b3  call    ?NlpReadCacheEntry@@YAJPEAU_UNICODE_STRING@@0KPEAKPEAPEAU_LOGON_CACHE_ENTRY@@1@Z; NlpReadCacheEntry(_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong *,_LOGON_CACHE_ENTRY * *,ulong *)
0x1800446b8  mov     esi, eax
0x1800446ba  test    eax, eax
0x1800446bc  js      short loc_18004472A
0x1800446be  dec     r12d
0x1800446c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446c8  cmp     rcx, r15
0x1800446cb  jz      short loc_1800446F6
0x1800446cd  test    byte ptr [rcx+1Ch], 2
0x1800446d1  jz      short loc_1800446F6
0x1800446d3  mov     r9d, dword ptr [rbp+Size+4]
0x1800446d7  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x1800446de  mov     rcx, [rcx+10h]
0x1800446e2  mov     edx, 1Bh
0x1800446e7  mov     [rsp+58h+var_30], rbx
0x1800446ec  mov     [rsp+58h+var_38], r14
0x1800446f1  call    WPP_SF_dZZ
0x1800446f6  mov     rbx, [rbp+var_20]
0x1800446fa  movzx   r8d, r13w
0x1800446fe  mov     r14d, dword ptr [rbp+Size]
0x180044702  mov     ecx, 0C0000072h
0x180044707  mov     r9d, dword ptr [rbp+Size+4]
0x18004470b  movzx   edx, [rbp+arg_8]
0x18004470f  mov     [rsp+58h+var_30], rbx
0x180044714  mov     dword ptr [rsp+58h+var_38], r14d
0x180044719  call    NlpDeleteCacheEntryInternal
0x18004471e  mov     esi, eax
0x180044720  test    eax, eax
0x180044722  jns     loc_18004464D
0x180044728  jmp     short loc_180044732
0x18004472a  mov     rbx, [rbp+var_20]
0x18004472e  mov     r14d, dword ptr [rbp+Size]
0x180044732  lea     rcx, NlpLogonCacheCritSec; Resource
0x180044739  call    cs:__imp_RtlReleaseResource
0x18004473f  test    rbx, rbx
0x180044742  jz      short loc_180044760
0x180044744  mov     r8d, r14d; Size
0x180044747  xor     edx, edx; Val
0x180044749  mov     rcx, rbx; void *
0x18004474c  call    memset_0
0x180044751  mov     rax, cs:qword_180088398
0x180044758  mov     rcx, rbx
0x18004475b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044760  test    rdi, rdi
0x180044763  jz      short loc_18004476E
0x180044765  mov     rcx, rdi; hMem
0x180044768  call    cs:__imp_LocalFree
0x18004476e  mov     eax, esi
0x180044770  add     rsp, 58h
0x180044774  pop     r15
0x180044776  pop     r14
0x180044778  pop     r13
0x18004477a  pop     r12
0x18004477c  pop     rdi
0x18004477d  pop     rsi
0x18004477e  pop     rbx
0x18004477f  pop     rbp
0x180044780  retn
```
