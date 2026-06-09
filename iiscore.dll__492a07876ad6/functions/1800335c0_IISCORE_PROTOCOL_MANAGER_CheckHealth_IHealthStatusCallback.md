# IISCORE_PROTOCOL_MANAGER::CheckHealth(IHealthStatusCallback *)

- ea: `0x1800335c0`
- end: `0x1800336b7`
- name: `?CheckHealth@IISCORE_PROTOCOL_MANAGER@@UEAAJPEAVIHealthStatusCallback@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this, struct IHealthStatusCallback *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800335c0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003361d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003361d`
- `iisutil!PuDbgPrint` at `0x180033668`
- `iisutil!PuDbgPrint` at `0x180033668`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033698`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033698`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800335d9`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800335d9`
- `W3TP!ThreadPoolPostCompletion` at `0x18003360d`
- `W3TP!ThreadPoolPostCompletion` at `0x18003360d`

## string_xrefs

- `0x180033648`: `Posting completion for ping handling failed`
- `0x18003364f`: `IISCORE_PROTOCOL_MANAGER::CheckHealth`
- `0x180033661`: `servercommon\inetsrv\iis\iisrearc\iis70\core\iiscore_protocol_manager.cxx`

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
0x1800335c0  mov     [rsp+arg_0], rbx
0x1800335c5  mov     [rsp+arg_8], rsi
0x1800335ca  push    rdi
0x1800335cb  sub     rsp, 30h
0x1800335cf  lea     rsi, [rcx+58h]
0x1800335d3  mov     rdi, rdx
0x1800335d6  mov     rcx, rsi
0x1800335d9  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800335e0  nop     dword ptr [rax+rax+00h]
0x1800335e5  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x1800335ed  mov     rcx, rdi
0x1800335f0  mov     rax, [rdi]
0x1800335f3  jz      loc_180033685
0x1800335f9  mov     rax, [rax]
0x1800335fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033601  mov     r8, rdi
0x180033604  lea     rdx, ?CheckHealth@W3_SERVER@@SAXKKPEAU_OVERLAPPED@@@Z; W3_SERVER::CheckHealth(ulong,ulong,_OVERLAPPED *)
0x18003360b  xor     ecx, ecx
0x18003360d  call    cs:__imp_?ThreadPoolPostCompletion@@YAHKP6AXKKPEAU_OVERLAPPED@@@Z0@Z; ThreadPoolPostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),_OVERLAPPED *)
0x180033614  nop     dword ptr [rax+rax+00h]
0x180033619  test    eax, eax
0x18003361b  jnz     short loc_180033693
0x18003361d  call    cs:__imp_GetLastError
0x180033624  nop     dword ptr [rax+rax+00h]
0x180033629  mov     ebx, eax
0x18003362b  test    eax, eax
0x18003362d  jle     short loc_180033638
0x18003362f  movzx   ebx, ax
0x180033632  or      ebx, 80070000h
0x180033638  test    byte ptr cs:g_dwDebugFlags, 3
0x18003363f  jz      short loc_180033674
0x180033641  mov     rcx, cs:g_pDebug
0x180033648  lea     rax, aPostingComplet; "Posting completion for ping handling fa"...
0x18003364f  lea     r9, aIiscoreProtoco; "IISCORE_PROTOCOL_MANAGER::CheckHealth"
0x180033656  mov     [rsp+38h+var_18], rax
0x18003365b  mov     r8d, 38Bh
0x180033661  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180033668  call    cs:__imp_PuDbgPrint
0x18003366f  nop     dword ptr [rax+rax+00h]
0x180033674  mov     rax, [rdi]
0x180033677  mov     rcx, rdi
0x18003367a  mov     rax, [rax+8]
0x18003367e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033683  jmp     short loc_180033695
0x180033685  mov     rax, [rax+10h]
0x180033689  mov     edx, 1
0x18003368e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033693  xor     ebx, ebx
0x180033695  mov     rcx, rsi
0x180033698  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18003369f  nop     dword ptr [rax+rax+00h]
0x1800336a4  mov     rsi, [rsp+38h+arg_8]
0x1800336a9  mov     eax, ebx
0x1800336ab  mov     rbx, [rsp+38h+arg_0]
0x1800336b0  add     rsp, 30h
0x1800336b4  pop     rdi
0x1800336b5  retn
```
