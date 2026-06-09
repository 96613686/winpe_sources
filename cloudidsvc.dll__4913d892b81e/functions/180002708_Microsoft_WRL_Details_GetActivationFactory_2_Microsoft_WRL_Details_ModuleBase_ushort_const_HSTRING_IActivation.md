# Microsoft::WRL::Details::GetActivationFactory<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180002708`
- end: `0x18000287f`
- name: `??$GetActivationFactory@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800026f0`

## callees

- `0x180001a50`
- `0x180002708`
- `0x180005324`
- `0x1800061b0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180002776`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180002776`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180002742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180002742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180002758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180002758`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180002856`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180002856`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180002817`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180002817`

## string_xrefs

- `0x18000281f`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetActivationFactory<2>(
        Microsoft::WRL::Details *this,
        __int64 a2,
        HSTRING a3,
        RTL_SRWLOCK *a4)
{
  PCWSTR StringRawBuffer; // r15
  const struct _GUID **v8; // rbx
  unsigned __int64 v9; // rbp
  unsigned int *v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  unsigned __int16 *v13; // rcx
  __int64 v14; // rax
  int v15; // edx
  unsigned int v17; // ebx
  struct IUnknown **v18; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v20; // [rsp+34h] [rbp-64h] BYREF
  __int128 v21; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v22[22]; // [rsp+48h] [rbp-50h]

  a4->Ptr = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(a3) || WindowsStringHasEmbeddedNull(a3, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v21 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v22 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v22[14] = *(_QWORD *)L"sId";
    v17 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v21);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    v8 = (const struct _GUID **)((*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 40LL))(this)
                               + 8);
    v9 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
    while ( (unsigned __int64)v8 < v9 )
    {
      if ( *v8
        && Microsoft::WRL::Details::IsServerNameEqual((Microsoft::WRL::Details *)*v8, 0, (const unsigned __int16 *)v10) )
      {
        v12 = (*(__int64 (**)(void))(v11 + 8))();
        v13 = (unsigned __int16 *)StringRawBuffer;
        v14 = v12 - (_QWORD)StringRawBuffer;
        do
        {
          v10 = (unsigned int *)*(unsigned __int16 *)((char *)v13 + v14);
          v15 = *v13 - (_DWORD)v10;
          if ( v15 )
            break;
          ++v13;
        }
        while ( (_DWORD)v10 );
        if ( !v15 )
        {
          v20 = 2;
          return Microsoft::WRL::Details::GetCacheEntry(
                   this,
                   (struct Microsoft::WRL::Details::ModuleBase *)&v20,
                   v10,
                   *v8,
                   a4,
                   v18);
        }
      }
      ++v8;
    }
    v17 = -2147221231;
    RoOriginateError(2147746065LL, a3);
  }
  return v17;
}

```

## disassembly

```asm
0x180002708  mov     [rsp+arg_8], rbx
0x18000270d  push    rbp
0x18000270e  push    rsi
0x18000270f  push    rdi
0x180002710  push    r14
0x180002712  push    r15
0x180002714  sub     rsp, 70h
0x180002718  mov     rax, cs:__security_cookie
0x18000271f  xor     rax, rsp
0x180002722  mov     [rsp+98h+var_38], rax
0x180002727  mov     r14, r9
0x18000272a  mov     rdi, r8
0x18000272d  mov     rsi, rcx
0x180002730  mov     qword ptr [r9], 0
0x180002737  mov     [rsp+98h+hasEmbedNull], 0
0x18000273f  mov     rcx, r8; string
0x180002742  call    cs:__imp_WindowsIsStringEmpty
0x180002748  test    eax, eax
0x18000274a  jnz     loc_18000281F
0x180002750  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180002755  mov     rcx, rdi; string
0x180002758  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18000275e  test    eax, eax
0x180002760  js      loc_18000281F
0x180002766  cmp     [rsp+98h+hasEmbedNull], 1
0x18000276b  jz      loc_18000281F
0x180002771  xor     edx, edx; length
0x180002773  mov     rcx, rdi; string
0x180002776  call    cs:__imp_WindowsGetStringRawBuffer
0x18000277c  mov     r15, rax
0x18000277f  mov     rcx, [rsi]
0x180002782  mov     rax, [rcx+28h]
0x180002786  mov     rcx, rsi
0x180002789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000278e  lea     rbx, [rax+8]
0x180002792  mov     rcx, [rsi]
0x180002795  mov     rax, [rcx+30h]
0x180002799  mov     rcx, rsi
0x18000279c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027a1  mov     rbp, rax
0x1800027a4  cmp     rbx, rbp
0x1800027a7  jnb     short loc_18000280D
0x1800027a9  mov     r9, [rbx]
0x1800027ac  test    r9, r9
0x1800027af  jz      short loc_1800027E8
0x1800027b1  xor     edx, edx; struct Microsoft::WRL::Details::CreatorMap *
0x1800027b3  mov     rcx, r9; this
0x1800027b6  call    ?IsServerNameEqual@Details@WRL@Microsoft@@YA_NPEBUCreatorMap@123@PEBG@Z; Microsoft::WRL::Details::IsServerNameEqual(Microsoft::WRL::Details::CreatorMap const *,ushort const *)
0x1800027bb  test    al, al
0x1800027bd  jz      short loc_1800027E8
0x1800027bf  mov     rax, [r9+8]
0x1800027c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027c8  mov     rcx, r15
0x1800027cb  sub     rax, r15
0x1800027ce  movzx   edx, word ptr [rcx]
0x1800027d1  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x1800027d6  sub     edx, r8d
0x1800027d9  jnz     short loc_1800027E4
0x1800027db  add     rcx, 2
0x1800027df  test    r8d, r8d
0x1800027e2  jnz     short loc_1800027CE
0x1800027e4  test    edx, edx
0x1800027e6  jz      short loc_1800027EE
0x1800027e8  add     rbx, 8
0x1800027ec  jmp     short loc_1800027A4
0x1800027ee  mov     [rsp+98h+var_64], 2
0x1800027f6  mov     [rsp+98h+SRWLock], r14; SRWLock
0x1800027fb  mov     r9, [rbx]; struct _GUID *
0x1800027fe  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180002803  mov     rcx, rsi; this
0x180002806  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000280b  jmp     short loc_18000285E
0x18000280d  mov     rdx, rdi
0x180002810  mov     ebx, 80040111h
0x180002815  mov     ecx, ebx
0x180002817  call    cs:__imp_RoOriginateError
0x18000281d  jmp     short loc_18000285C
0x18000281f  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180002826  movups  [rsp+98h+var_60], xmm0
0x18000282b  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180002832  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180002837  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x18000283f  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180002845  lea     r8, [rsp+98h+var_60]
0x18000284a  mov     edx, 12h
0x18000284f  mov     ebx, 80070057h
0x180002854  mov     ecx, ebx
0x180002856  call    cs:__imp_RoOriginateErrorW
0x18000285c  mov     eax, ebx
0x18000285e  mov     rcx, [rsp+98h+var_38]
0x180002863  xor     rcx, rsp; StackCookie
0x180002866  call    __security_check_cookie
0x18000286b  mov     rbx, [rsp+98h+arg_8]
0x180002873  add     rsp, 70h
0x180002877  pop     r15
0x180002879  pop     r14
0x18000287b  pop     rdi
0x18000287c  pop     rsi
0x18000287d  pop     rbp
0x18000287e  retn
```
