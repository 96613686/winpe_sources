# ISAPI_REQUEST::SetupHttpCachedResponse(_HTTP_CACHE_POLICY *)

- ea: `0x1800100ac`
- end: `0x180010202`
- name: `?SetupHttpCachedResponse@ISAPI_REQUEST@@AEAAJPEAU_HTTP_CACHE_POLICY@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *__hidden this, struct _HTTP_CACHE_POLICY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180010460`

## callees

- `0x1800100ac`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010179`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010179`
- `iisutil!StringTimeToFileTime` at `0x18001016a`
- `iisutil!StringTimeToFileTime` at `0x18001016a`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::SetupHttpCachedResponse(ISAPI_REQUEST *this, struct _HTTP_CACHE_POLICY *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  const char *v6; // rax
  HTTP_CACHE_POLICY_TYPE v7; // eax
  __int64 v8; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF
  union _LARGE_INTEGER v11; // [rsp+40h] [rbp+18h] BYREF

  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 32LL))(*((_QWORD *)this + 3));
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v4 + 120LL))(v4) )
    return 2147942450LL;
  if ( *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4) + 8) != 200 )
    return 2147942450LL;
  v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3));
  if ( *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5) + 36) != 4 )
    return 2147942450LL;
  v6 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 64LL))(v4, 18);
  if ( !v6 )
  {
    v7 = HttpCachePolicyUserInvalidates;
    goto LABEL_9;
  }
  v11.QuadPart = 0;
  SystemTimeAsFileTime = 0;
  if ( !StringTimeToFileTime(v6, &v11) )
    return 2147942450LL;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( v11.QuadPart <= *(_QWORD *)&SystemTimeAsFileTime )
    return 2147942450LL;
  v7 = HttpCachePolicyTimeToLive;
  a2->SecondsToLive = (v11.QuadPart - *(_QWORD *)&SystemTimeAsFileTime) / 10000000;
LABEL_9:
  a2->Policy = v7;
  if ( ISAPI_REQUEST::sm_fDontFlushCachedResponses )
  {
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x1800100ac  mov     [rsp+arg_8], rbx
0x1800100b1  mov     [rsp+arg_18], rsi
0x1800100b6  push    rdi
0x1800100b7  sub     rsp, 20h
0x1800100bb  mov     rsi, rcx
0x1800100be  mov     rdi, rdx
0x1800100c1  mov     rcx, [rcx+18h]
0x1800100c5  mov     rax, [rcx]
0x1800100c8  mov     rax, [rax+20h]
0x1800100cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100d1  mov     rbx, rax
0x1800100d4  mov     rcx, rax
0x1800100d7  mov     r8, [rax]
0x1800100da  mov     rax, [r8+78h]
0x1800100de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100e3  test    eax, eax
0x1800100e5  jz      loc_1800101ED
0x1800100eb  mov     rcx, [rbx]
0x1800100ee  mov     rax, [rcx+8]
0x1800100f2  mov     rcx, rbx
0x1800100f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100fa  mov     ecx, 0C8h
0x1800100ff  cmp     [rax+8], cx
0x180010103  jnz     loc_1800101ED
0x180010109  mov     rcx, [rsi+18h]
0x18001010d  mov     rax, [rcx]
0x180010110  mov     rax, [rax+18h]
0x180010114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010119  mov     rdx, rax
0x18001011c  mov     rcx, [rax]
0x18001011f  mov     rax, [rcx+8]
0x180010123  mov     rcx, rdx
0x180010126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001012b  cmp     dword ptr [rax+24h], 4
0x18001012f  jnz     loc_1800101ED
0x180010135  mov     rax, [rbx]
0x180010138  xor     r8d, r8d
0x18001013b  mov     rcx, rbx
0x18001013e  mov     rax, [rax+40h]
0x180010142  lea     edx, [r8+12h]
0x180010146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001014b  test    rax, rax
0x18001014e  jz      short loc_1800101B8
0x180010150  lea     rdx, [rsp+28h+arg_10]
0x180010155  mov     [rsp+28h+arg_10], 0
0x18001015e  mov     rcx, rax
0x180010161  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001016a  call    cs:__imp_?StringTimeToFileTime@@YAHPEBDPEAT_LARGE_INTEGER@@@Z; StringTimeToFileTime(char const *,_LARGE_INTEGER *)
0x180010170  test    eax, eax
0x180010172  jz      short loc_1800101ED
0x180010174  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010179  call    cs:__imp_GetSystemTimeAsFileTime
0x18001017f  mov     rcx, [rsp+28h+arg_10]
0x180010184  cmp     rcx, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x180010189  jle     short loc_1800101ED
0x18001018b  sub     rcx, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x180010190  mov     rax, 0D6BF94D5E57A42BDh
0x18001019a  imul    rcx
0x18001019d  add     rdx, rcx
0x1800101a0  sar     rdx, 17h
0x1800101a4  mov     rax, rdx
0x1800101a7  shr     rax, 3Fh
0x1800101ab  add     rdx, rax
0x1800101ae  mov     eax, 2
0x1800101b3  mov     [rdi+4], edx
0x1800101b6  jmp     short loc_1800101BD
0x1800101b8  mov     eax, 1
0x1800101bd  mov     [rdi], eax
0x1800101bf  cmp     cs:?sm_fDontFlushCachedResponses@ISAPI_REQUEST@@0HA, 0; int ISAPI_REQUEST::sm_fDontFlushCachedResponses
0x1800101c6  jz      short loc_1800101E9
0x1800101c8  mov     rax, [rbx]
0x1800101cb  mov     rcx, rbx
0x1800101ce  mov     rax, [rax+10h]
0x1800101d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101d7  mov     rdx, rax
0x1800101da  mov     rcx, [rax]
0x1800101dd  mov     rax, [rcx+8]
0x1800101e1  mov     rcx, rdx
0x1800101e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101e9  xor     eax, eax
0x1800101eb  jmp     short loc_1800101F2
0x1800101ed  mov     eax, 80070032h
0x1800101f2  mov     rbx, [rsp+28h+arg_8]
0x1800101f7  mov     rsi, [rsp+28h+arg_18]
0x1800101fc  add     rsp, 20h
0x180010200  pop     rdi
0x180010201  retn
```
