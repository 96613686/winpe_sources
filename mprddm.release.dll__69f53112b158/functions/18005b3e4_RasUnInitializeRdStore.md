# RasUnInitializeRdStore

- ea: `0x18005b3e4`
- end: `0x18005b4dc`
- name: `RasUnInitializeRdStore`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800593c4`

## callees

- `0x180001328`
- `0x180059c08`
- `0x18005b3e4`
- `0x180062284`
- `0x180062cf4`
- `0x1800753f4`
- `0x1800754ac`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18005b4b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005b4b3`
- `KERNEL32!DeleteCriticalSection` at `0x18005b481`
- `KERNEL32!DeleteCriticalSection` at `0x18005b481`

## pseudocode

```c
__int64 __fastcall RasUnInitializeRdStore(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))
{
  RRasIPAddressMgr *v4; // rbx
  RRasIPAddressMgr *v5; // rax
  unsigned int v6; // eax
  bool v7; // zf
  unsigned int v8; // edi
  RRasIPAddressMgr *v9; // rbx
  __int64 v11; // [rsp+20h] [rbp-40h] BYREF
  __int128 v12; // [rsp+28h] [rbp-38h]
  __int128 v13; // [rsp+38h] [rbp-28h]
  __int64 v14; // [rsp+48h] [rbp-18h]
  int v15; // [rsp+50h] [rbp-10h]
  int v16; // [rsp+54h] [rbp-Ch]
  unsigned int v17; // [rsp+70h] [rbp+10h] BYREF

  v4 = RRasIPAddressMgr::rdStoreObj;
  if ( !RRasIPAddressMgr::rdStoreObj )
  {
    v5 = (RRasIPAddressMgr *)operator new(0xA8u);
    if ( v5 )
      v4 = RRasIPAddressMgr::RRasIPAddressMgr(v5);
    else
      v4 = 0;
    RRasIPAddressMgr::rdStoreObj = v4;
  }
  v17 = 0;
  v11 = 0;
  v14 = 0;
  v15 = -1;
  v16 = 0;
  v12 = 0;
  v13 = 0;
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v11,
      L"RRasIPAddressMgr::UnInitializeRdStore",
      &v17,
      a4);
  v6 = RRasIPAddressMgr::CleanUpRdStore(v4);
  v7 = *(_DWORD *)v4 == 1;
  v8 = v6;
  v17 = v6;
  if ( v7 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 8));
    *(_DWORD *)v4 = 0;
    v8 = v17;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v11);
  v9 = RRasIPAddressMgr::rdStoreObj;
  if ( RRasIPAddressMgr::rdStoreObj )
  {
    RRasIPAddressMgr::~RRasIPAddressMgr(RRasIPAddressMgr::rdStoreObj);
    operator delete(v9);
    RRasIPAddressMgr::rdStoreObj = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18005b3e4  mov     [rsp-8+arg_8], rbx
0x18005b3e9  mov     [rsp-8+arg_10], rdi
0x18005b3ee  push    rbp
0x18005b3ef  mov     rbp, rsp
0x18005b3f2  sub     rsp, 60h
0x18005b3f6  mov     rbx, cs:?rdStoreObj@RRasIPAddressMgr@@0PEAV1@EA; RRasIPAddressMgr * RRasIPAddressMgr::rdStoreObj
0x18005b3fd  test    rbx, rbx
0x18005b400  jnz     short loc_18005B427
0x18005b402  mov     ecx, 0A8h; Size
0x18005b407  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005b40c  test    rax, rax
0x18005b40f  jz      short loc_18005B41E
0x18005b411  mov     rcx, rax; this
0x18005b414  call    ??0RRasIPAddressMgr@@AEAA@XZ; RRasIPAddressMgr::RRasIPAddressMgr(void)
0x18005b419  mov     rbx, rax
0x18005b41c  jmp     short loc_18005B420
0x18005b41e  xor     ebx, ebx
0x18005b420  mov     cs:?rdStoreObj@RRasIPAddressMgr@@0PEAV1@EA, rbx; RRasIPAddressMgr * RRasIPAddressMgr::rdStoreObj
0x18005b427  and     [rbp+arg_0], 0
0x18005b42b  xorps   xmm0, xmm0
0x18005b42e  and     [rbp+var_40], 0
0x18005b433  xorps   xmm1, xmm1
0x18005b436  and     [rbp+var_18], 0
0x18005b43b  or      [rbp+var_10], 0FFFFFFFFh
0x18005b43f  and     [rbp+var_C], 0
0x18005b443  cmp     qword ptr cs:xmmword_1800D0740+8, 0
0x18005b44b  movdqu  [rbp+var_38], xmm0
0x18005b450  movdqu  [rbp+var_28], xmm1
0x18005b455  jz      short loc_18005B46B
0x18005b457  lea     r8, [rbp+arg_0]; unsigned int *
0x18005b45b  lea     rdx, aRrasipaddressm_0; "RRasIPAddressMgr::UnInitializeRdStore"
0x18005b462  lea     rcx, [rbp+var_40]; this
0x18005b466  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18005b46b  mov     rcx, rbx; this
0x18005b46e  call    ?CleanUpRdStore@RRasIPAddressMgr@@AEAAKXZ; RRasIPAddressMgr::CleanUpRdStore(void)
0x18005b473  cmp     dword ptr [rbx], 1
0x18005b476  mov     edi, eax
0x18005b478  mov     [rbp+arg_0], eax
0x18005b47b  jnz     short loc_18005B493
0x18005b47d  lea     rcx, [rbx+8]; lpCriticalSection
0x18005b481  call    cs:__imp_DeleteCriticalSection
0x18005b488  nop     dword ptr [rax+rax+00h]
0x18005b48d  and     dword ptr [rbx], 0
0x18005b490  mov     edi, [rbp+arg_0]
0x18005b493  lea     rcx, [rbp+var_40]; this
0x18005b497  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18005b49c  mov     rbx, cs:?rdStoreObj@RRasIPAddressMgr@@0PEAV1@EA; RRasIPAddressMgr * RRasIPAddressMgr::rdStoreObj
0x18005b4a3  test    rbx, rbx
0x18005b4a6  jz      short loc_18005B4C7
0x18005b4a8  mov     rcx, rbx; this
0x18005b4ab  call    ??1RRasIPAddressMgr@@QEAA@XZ; RRasIPAddressMgr::~RRasIPAddressMgr(void)
0x18005b4b0  mov     rcx, rbx
0x18005b4b3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18005b4ba  nop     dword ptr [rax+rax+00h]
0x18005b4bf  and     cs:?rdStoreObj@RRasIPAddressMgr@@0PEAV1@EA, 0; RRasIPAddressMgr * RRasIPAddressMgr::rdStoreObj
0x18005b4c7  lea     r11, [rsp+60h+var_s0]
0x18005b4cc  mov     eax, edi
0x18005b4ce  mov     rbx, [r11+18h]
0x18005b4d2  mov     rdi, [r11+20h]
0x18005b4d6  mov     rsp, r11
0x18005b4d9  pop     rbp
0x18005b4da  retn
```
