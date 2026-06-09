# IP_MODULE::TableIterator(STTABLE_ITEM *,unsigned __int64,int *)

- ea: `0x18000658c`
- end: `0x18000666c`
- name: `?TableIterator@IP_MODULE@@CAXPEAVSTTABLE_ITEM@@_KPEAH@Z`
- size: `224`
- prototype: `void __fastcall(struct STTABLE_ITEM *, unsigned __int64, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006074`

## callees

- `0x18000658c`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800065bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800065bc`
- `iisutil!PuDbgPrint` at `0x180006630`
- `iisutil!PuDbgPrint` at `0x180006630`

## string_xrefs

- `0x1800065ed`: `servercommon\inetsrv\iis\iisrearc\iis70\dynamiciprestriction\dipmodule.cpp`

## pseudocode

```c
void __fastcall IP_MODULE::TableIterator(struct STTABLE_ITEM *a1, __int64 a2, int *a3)
{
  __int64 v5; // rbx

  *a3 = 0;
  if ( !*((_DWORD *)a1 + 56) )
  {
    v5 = *((_QWORD *)a1 + 29);
    if ( GetTickCount64() - v5 > *((unsigned int *)a1 + 60) )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        *(_BYTE *)(*((unsigned int *)a1 + 36) + *((_QWORD *)a1 + 17)) = 0;
        *(_BYTE *)((unsigned int)(*((_DWORD *)a1 + 36) + 1) + *((_QWORD *)a1 + 17)) = 0;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\dynamiciprestriction\\dipmodule.cpp",
          1167,
          "IP_MODULE::TableIterator",
          "Marking record for client %s for deletion.\n",
          *((const char **)a1 + 17));
      }
      *a3 = 1;
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 6, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(struct STTABLE_ITEM *, __int64))a1)(a1, 1);
}

```

## disassembly

```asm
0x18000658c  mov     [rsp+arg_8], rbx
0x180006591  mov     [rsp+arg_10], rsi
0x180006596  push    rdi
0x180006597  sub     rsp, 30h
0x18000659b  mov     dword ptr [r8], 0
0x1800065a2  mov     rsi, r8
0x1800065a5  cmp     dword ptr [rcx+0E0h], 0
0x1800065ac  mov     rdi, rcx
0x1800065af  jnz     loc_18000663C
0x1800065b5  mov     rbx, [rcx+0E8h]
0x1800065bc  call    cs:__imp_GetTickCount64
0x1800065c2  mov     edx, [rdi+0F0h]
0x1800065c8  sub     rax, rbx
0x1800065cb  cmp     rax, rdx
0x1800065ce  jbe     short loc_18000663C
0x1800065d0  test    byte ptr cs:g_dwDebugFlags, 3
0x1800065d7  jz      short loc_180006636
0x1800065d9  mov     ecx, [rdi+90h]
0x1800065df  lea     r9, aIpModuleTablei; "IP_MODULE::TableIterator"
0x1800065e6  mov     rax, [rdi+88h]
0x1800065ed  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800065f4  mov     r8d, 48Fh
0x1800065fa  mov     byte ptr [rcx+rax], 0
0x1800065fe  mov     ecx, [rdi+90h]
0x180006604  mov     rax, [rdi+88h]
0x18000660b  inc     ecx
0x18000660d  mov     byte ptr [rcx+rax], 0
0x180006611  mov     rax, [rdi+88h]
0x180006618  mov     rcx, cs:g_pDebug
0x18000661f  mov     [rsp+38h+var_10], rax
0x180006624  lea     rax, aMarkingRecordF; "Marking record for client %s for deleti"...
0x18000662b  mov     [rsp+38h+var_18], rax
0x180006630  call    cs:__imp_PuDbgPrint
0x180006636  mov     dword ptr [rsi], 1
0x18000663c  or      eax, 0FFFFFFFFh
0x18000663f  lock xadd [rdi+18h], eax
0x180006644  cmp     eax, 1
0x180006647  jnz     short loc_18000665C
0x180006649  mov     rax, [rdi]
0x18000664c  mov     edx, 1
0x180006651  mov     rcx, rdi
0x180006654  mov     rax, [rax]
0x180006657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000665c  mov     rbx, [rsp+38h+arg_8]
0x180006661  mov     rsi, [rsp+38h+arg_10]
0x180006666  add     rsp, 30h
0x18000666a  pop     rdi
0x18000666b  retn
```
