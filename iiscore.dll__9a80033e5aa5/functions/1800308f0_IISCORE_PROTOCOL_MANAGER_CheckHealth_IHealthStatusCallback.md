# IISCORE_PROTOCOL_MANAGER::CheckHealth(IHealthStatusCallback *)

- ea: `0x1800308f0`
- end: `0x1800309c4`
- name: `?CheckHealth@IISCORE_PROTOCOL_MANAGER@@UEAAJPEAVIHealthStatusCallback@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this, struct IHealthStatusCallback *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800308f0`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003093d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003093d`
- `iisutil!PuDbgPrint` at `0x180030982`
- `iisutil!PuDbgPrint` at `0x180030982`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800309ac`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800309ac`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180030909`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180030909`
- `W3TP!ThreadPoolPostCompletion` at `0x180030933`
- `W3TP!ThreadPoolPostCompletion` at `0x180030933`

## string_xrefs

- `0x180030962`: `Posting completion for ping handling failed`
- `0x180030969`: `IISCORE_PROTOCOL_MANAGER::CheckHealth`
- `0x18003097b`: `servercommon\inetsrv\iis\iisrearc\iis70\core\iiscore_protocol_manager.cxx`

## pseudocode

```c
__int64 __fastcall IISCORE_PROTOCOL_MANAGER::CheckHealth(IISCORE_PROTOCOL_MANAGER *this, struct _OVERLAPPED *a2)
{
  CReaderWriterLock3 *v2; // rsi
  ULONG_PTR Internal; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx

  v2 = (IISCORE_PROTOCOL_MANAGER *)((char *)this + 88);
  CReaderWriterLock3::ReadLock((IISCORE_PROTOCOL_MANAGER *)((char *)this + 88));
  Internal = a2->Internal;
  if ( !g_pW3Server )
  {
    (*(void (__fastcall **)(struct _OVERLAPPED *, __int64))(Internal + 16))(a2, 1);
    goto LABEL_9;
  }
  (*(void (__fastcall **)(struct _OVERLAPPED *))Internal)(a2);
  if ( ThreadPoolPostCompletion(
         0,
         (void (*)(unsigned int, unsigned int, struct _OVERLAPPED *))W3_SERVER::CheckHealth,
         a2) )
  {
LABEL_9:
    v6 = 0;
    goto LABEL_10;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\iiscore_protocol_manager.cxx",
      907,
      "IISCORE_PROTOCOL_MANAGER::CheckHealth",
      "Posting completion for ping handling failed");
  (*(void (__fastcall **)(struct _OVERLAPPED *))(a2->Internal + 8))(a2);
LABEL_10:
  CReaderWriterLock3::ReadUnlock(v2);
  return v6;
}

```

## disassembly

```asm
0x1800308f0  mov     [rsp+arg_0], rbx
0x1800308f5  mov     [rsp+arg_8], rsi
0x1800308fa  push    rdi
0x1800308fb  sub     rsp, 30h
0x1800308ff  lea     rsi, [rcx+58h]
0x180030903  mov     rdi, rdx
0x180030906  mov     rcx, rsi
0x180030909  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18003090f  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180030917  mov     rcx, rdi
0x18003091a  mov     rax, [rdi]
0x18003091d  jz      short loc_180030999
0x18003091f  mov     rax, [rax]
0x180030922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030927  mov     r8, rdi
0x18003092a  lea     rdx, ?CheckHealth@W3_SERVER@@SAXKKPEAU_OVERLAPPED@@@Z; W3_SERVER::CheckHealth(ulong,ulong,_OVERLAPPED *)
0x180030931  xor     ecx, ecx
0x180030933  call    cs:__imp_?ThreadPoolPostCompletion@@YAHKP6AXKKPEAU_OVERLAPPED@@@Z0@Z; ThreadPoolPostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),_OVERLAPPED *)
0x180030939  test    eax, eax
0x18003093b  jnz     short loc_1800309A7
0x18003093d  call    cs:__imp_GetLastError
0x180030943  mov     ebx, eax
0x180030945  test    eax, eax
0x180030947  jle     short loc_180030952
0x180030949  movzx   ebx, ax
0x18003094c  or      ebx, 80070000h
0x180030952  test    byte ptr cs:g_dwDebugFlags, 3
0x180030959  jz      short loc_180030988
0x18003095b  mov     rcx, cs:g_pDebug
0x180030962  lea     rax, aPostingComplet; "Posting completion for ping handling fa"...
0x180030969  lea     r9, aIiscoreProtoco; "IISCORE_PROTOCOL_MANAGER::CheckHealth"
0x180030970  mov     [rsp+38h+var_18], rax
0x180030975  mov     r8d, 38Bh
0x18003097b  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180030982  call    cs:__imp_PuDbgPrint
0x180030988  mov     rax, [rdi]
0x18003098b  mov     rcx, rdi
0x18003098e  mov     rax, [rax+8]
0x180030992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030997  jmp     short loc_1800309A9
0x180030999  mov     rax, [rax+10h]
0x18003099d  mov     edx, 1
0x1800309a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309a7  xor     ebx, ebx
0x1800309a9  mov     rcx, rsi
0x1800309ac  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800309b2  mov     rsi, [rsp+38h+arg_8]
0x1800309b7  mov     eax, ebx
0x1800309b9  mov     rbx, [rsp+38h+arg_0]
0x1800309be  add     rsp, 30h
0x1800309c2  pop     rdi
0x1800309c3  retn
```
