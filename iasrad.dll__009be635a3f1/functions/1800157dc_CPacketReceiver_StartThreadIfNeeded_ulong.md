# CPacketReceiver::StartThreadIfNeeded(ulong)

- ea: `0x1800157dc`
- end: `0x1800158ee`
- name: `?StartThreadIfNeeded@CPacketReceiver@@AEAAHK@Z`
- size: `274`
- prototype: `__int64 __fastcall(CPacketReceiver *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015604`
- `0x180015938`

## callees

- `0x1800094e4`
- `0x1800126b8`
- `0x1800157dc`
- `0x18001d31c`

## import_xrefs

- `iassvcs!IASRequestThread` at `0x18001586a`
- `iassvcs!IASRequestThread` at `0x18001586a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001587e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001587e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015802`

## string_xrefs

- `0x18001583e`: `CoTaskMemAlloc failed in CPacketReceiver::StartThreadIfNeeded.`
- `0x1800158a6`: `IASRequestThread failed in CPacketReceiver::StartThreadIfNeeded.`

## pseudocode

```c
__int64 __fastcall CPacketReceiver::StartThreadIfNeeded(CPacketReceiver *this, int a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rdx

  if ( (unsigned int)CPacketIo::IsProcessingEnabled(this) )
  {
    v4 = CoTaskMemAlloc(0x18u);
    if ( !v4 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      {
        return 0;
      }
      WppDbgPrint("CoTaskMemAlloc failed in CPacketReceiver::StartThreadIfNeeded.");
      v5 = 28;
LABEL_12:
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids, "NPSRAD");
      return 0;
    }
    v4[1] = this;
    *v4 = CPacketReceiver::CallbackRoutine;
    *((_DWORD *)v4 + 4) = a2;
    _InterlockedIncrement(&g_lThreadCount);
    if ( !(unsigned int)IASRequestThread(v4) )
    {
      _InterlockedDecrement(&g_lThreadCount);
      CoTaskMemFree(v4);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      {
        return 0;
      }
      WppDbgPrint("IASRequestThread failed in CPacketReceiver::StartThreadIfNeeded.");
      v5 = 29;
      goto LABEL_12;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800157dc  mov     [rsp+arg_0], rbx
0x1800157e1  mov     [rsp+arg_8], rsi
0x1800157e6  push    rdi
0x1800157e7  sub     rsp, 20h
0x1800157eb  mov     esi, edx
0x1800157ed  mov     rdi, rcx
0x1800157f0  call    ?IsProcessingEnabled@CPacketIo@@IEAAHXZ; CPacketIo::IsProcessingEnabled(void)
0x1800157f5  test    eax, eax
0x1800157f7  jz      loc_1800158D9
0x1800157fd  mov     ecx, 18h; cb
0x180015802  call    cs:__imp_CoTaskMemAlloc
0x180015808  mov     rbx, rax
0x18001580b  test    rax, rax
0x18001580e  jnz     short loc_18001584F
0x180015810  mov     rax, cs:WPP_GLOBAL_Control
0x180015817  lea     rcx, WPP_GLOBAL_Control
0x18001581e  cmp     rax, rcx
0x180015821  jz      loc_1800158D5
0x180015827  cmp     byte ptr [rax+19h], 2
0x18001582b  jb      loc_1800158D5
0x180015831  test    dword ptr [rax+1Ch], 100h
0x180015838  jz      loc_1800158D5
0x18001583e  lea     rcx, aCotaskmemalloc; "CoTaskMemAlloc failed in CPacketReceive"...
0x180015845  call    WppDbgPrint
0x18001584a  lea     edx, [rbx+1Ch]
0x18001584d  jmp     short loc_1800158B7
0x18001584f  lea     rax, ?CallbackRoutine@CPacketReceiver@@CAXPEAUIAS_CALLBACK@@@Z; CPacketReceiver::CallbackRoutine(IAS_CALLBACK *)
0x180015856  mov     [rbx+8], rdi
0x18001585a  mov     [rbx], rax
0x18001585d  mov     [rbx+10h], esi
0x180015860  lock inc cs:?g_lThreadCount@@3JA; long g_lThreadCount
0x180015867  mov     rcx, rbx
0x18001586a  call    cs:__imp_IASRequestThread
0x180015870  test    eax, eax
0x180015872  jnz     short loc_1800158D9
0x180015874  lock dec cs:?g_lThreadCount@@3JA; long g_lThreadCount
0x18001587b  mov     rcx, rbx; pv
0x18001587e  call    cs:__imp_CoTaskMemFree
0x180015884  mov     rax, cs:WPP_GLOBAL_Control
0x18001588b  lea     rcx, WPP_GLOBAL_Control
0x180015892  cmp     rax, rcx
0x180015895  jz      short loc_1800158D5
0x180015897  cmp     byte ptr [rax+19h], 2
0x18001589b  jb      short loc_1800158D5
0x18001589d  test    dword ptr [rax+1Ch], 100h
0x1800158a4  jz      short loc_1800158D5
0x1800158a6  lea     rcx, aIasrequestthre; "IASRequestThread failed in CPacketRecei"...
0x1800158ad  call    WppDbgPrint
0x1800158b2  mov     edx, 1Dh
0x1800158b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158be  lea     r9, aNpsrad; "NPSRAD"
0x1800158c5  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x1800158cc  mov     rcx, [rcx+10h]
0x1800158d0  call    WPP_SF_s
0x1800158d5  xor     eax, eax
0x1800158d7  jmp     short loc_1800158DE
0x1800158d9  mov     eax, 1
0x1800158de  mov     rbx, [rsp+28h+arg_0]
0x1800158e3  mov     rsi, [rsp+28h+arg_8]
0x1800158e8  add     rsp, 20h
0x1800158ec  pop     rdi
0x1800158ed  retn
```
