# CIEAdminBrokerClassFactory::Release(void)

- ea: `0x140004240`
- end: `0x1400042bd`
- name: `?Release@CIEAdminBrokerClassFactory@@UEAAKXZ`
- size: `125`
- prototype: `unsigned int __fastcall(CIEAdminBrokerClassFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400039bc`
- `0x140004240`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140004289`
- `KERNEL32!SetEvent` at `0x140004289`
- `USER32!PostQuitMessage` at `0x140004297`
- `USER32!PostQuitMessage` at `0x140004297`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerClassFactory::Release(CIEAdminBrokerClassFactory *this)
{
  int v1; // edi
  unsigned int v3; // edi

  v1 = *((_DWORD *)this + 2);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
  {
    v3 = 0;
    if ( this )
    {
      *(_QWORD *)this = &CIEAdminBrokerClassFactory::`vftable';
      if ( _InterlockedExchangeAdd(&g_ObjectCount, 0xFFFFFFFF) == 1 )
      {
        if ( g_hQuitEvent )
          SetEvent(g_hQuitEvent);
        PostQuitMessage(0);
      }
      operator delete(this);
    }
  }
  else
  {
    return (unsigned int)(v1 - 1);
  }
  return v3;
}

```

## disassembly

```asm
0x140004240  mov     [rsp+arg_0], rbx
0x140004245  push    rdi
0x140004246  sub     rsp, 20h
0x14000424a  mov     edi, [rcx+8]
0x14000424d  mov     rbx, rcx
0x140004250  or      ecx, 0FFFFFFFFh
0x140004253  mov     eax, ecx
0x140004255  lock xadd [rbx+8], eax
0x14000425a  add     eax, ecx
0x14000425c  jnz     short loc_1400042AD
0x14000425e  xor     edi, edi
0x140004260  test    rbx, rbx
0x140004263  jz      short loc_1400042AF
0x140004265  lea     rax, ??_7CIEAdminBrokerClassFactory@@6B@; const CIEAdminBrokerClassFactory::`vftable'
0x14000426c  mov     [rbx], rax
0x14000426f  mov     eax, ecx
0x140004271  lock xadd cs:?g_ObjectCount@@3JA, eax; long g_ObjectCount
0x140004279  add     eax, ecx
0x14000427b  jnz     short loc_1400042A3
0x14000427d  mov     rcx, cs:?g_hQuitEvent@@3PEAXEA; hEvent
0x140004284  test    rcx, rcx
0x140004287  jz      short loc_140004295
0x140004289  call    cs:__imp_SetEvent
0x140004290  nop     dword ptr [rax+rax+00h]
0x140004295  xor     ecx, ecx; nExitCode
0x140004297  call    cs:__imp_PostQuitMessage
0x14000429e  nop     dword ptr [rax+rax+00h]
0x1400042a3  mov     rcx, rbx; lpMem
0x1400042a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400042ab  jmp     short loc_1400042AF
0x1400042ad  dec     edi
0x1400042af  mov     rbx, [rsp+28h+arg_0]
0x1400042b4  mov     eax, edi
0x1400042b6  add     rsp, 20h
0x1400042ba  pop     rdi
0x1400042bb  retn
```
