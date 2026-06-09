# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,uint)

- ea: `0x10007f59`
- end: `0x1000803e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SGXPAUFailureInfo@3@PADI@Z`
- size: `229`
- prototype: `static void __stdcall(struct wil::FailureInfo *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10008050`

## callees

- `0x10007e9a`
- `0x10007f59`
- `0x1002d510`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x10007f81`
- `KERNEL32!GetCurrentThreadId` at `0x10007f81`

## pseudocode

```c
void __userpurge wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        struct wil::FailureInfo *a1@<edx>,
        int a2@<ecx>,
        struct wil::details::ThreadFailureCallbackHolder *a3,
        char *a4,
        unsigned int a5)
{
  char v7; // cl
  int v8; // ebx
  DWORD CurrentThreadId; // ecx
  int *i; // ebx
  int v11; // ebx
  char v12; // al
  bool v13; // al
  char *v14; // [esp+0h] [ebp-18h]
  unsigned int v15; // [esp+4h] [ebp-14h]
  char v16; // [esp+17h] [ebp-1h]

  v7 = 0;
  v16 = 0;
  LOBYTE(a1->type) = 0;
  v8 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    for ( i = *(int **)(v8 + 4 * ((CurrentThreadId >> 2) % 0xA)); i; i = (int *)i[1] )
    {
      if ( *i == CurrentThreadId )
      {
        i += 2;
        break;
      }
    }
    if ( i && *i )
    {
      LOBYTE(a1->type) = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(a1, a3, v14, v15) )
        *(_DWORD *)(a2 + 48) = a1;
      v11 = *i;
      do
      {
        v12 = *(_BYTE *)(v11 + 20);
        *(_BYTE *)(v11 + 20) = 1;
        if ( v12 )
        {
          v7 = v16;
        }
        else
        {
          v7 = (***(int (__thiscall ****)(_DWORD, int))(v11 + 4))(*(_DWORD *)(v11 + 4), a2) | v16;
          *(_BYTE *)(v11 + 20) = 0;
          v16 = v7;
        }
        v11 = *(_DWORD *)(v11 + 8);
      }
      while ( v11 );
    }
    else
    {
      v7 = 0;
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    v13 = v7 || (*(_BYTE *)(a2 + 4) & 2) != 0;
    ((void (__thiscall *)(CD3DSurfaceAllocator *, bool, int))wil::details::g_pfnTelemetryCallback)(
      wil::details::g_pfnTelemetryCallback,
      v13,
      a2);
  }
}

```

## disassembly

```asm
0x10007f59  mov     edi, edi
0x10007f5b  push    ebp
0x10007f5c  mov     ebp, esp
0x10007f5e  sub     esp, 0Ch
0x10007f61  push    ebx
0x10007f62  push    esi
0x10007f63  push    edi
0x10007f64  mov     edi, edx
0x10007f66  mov     esi, ecx
0x10007f68  xor     cl, cl
0x10007f6a  mov     [ebp+var_8], esi
0x10007f6d  mov     [ebp+var_1], cl
0x10007f70  mov     byte ptr [edi], 0
0x10007f73  mov     ebx, ?g_pThreadFailureCallbacks@details@wil@@3PAV?$ThreadLocalStorage@PAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x10007f79  test    ebx, ebx
0x10007f7b  jz      loc_10008010
0x10007f81  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10007f87  mov     ecx, eax
0x10007f89  mov     [ebp+var_C], 0Ah
0x10007f90  shr     eax, 2
0x10007f93  xor     edx, edx
0x10007f95  div     [ebp+var_C]
0x10007f98  mov     ebx, [ebx+edx*4]
0x10007f9b  jmp     short loc_10007FA4
0x10007f9d  cmp     [ebx], ecx
0x10007f9f  jz      short loc_10007FF9
0x10007fa1  mov     ebx, [ebx+4]
0x10007fa4  test    ebx, ebx
0x10007fa6  jnz     short loc_10007F9D
0x10007fa8  test    ebx, ebx
0x10007faa  jz      short loc_1000800D
0x10007fac  cmp     dword ptr [ebx], 0
0x10007faf  jz      short loc_1000800D
0x10007fb1  push    [ebp+arg_0]; struct wil::details::ThreadFailureCallbackHolder *
0x10007fb4  mov     byte ptr [edi], 0
0x10007fb7  mov     ecx, esi
0x10007fb9  mov     edx, [ebx]
0x10007fbb  push    edi; struct wil::FailureInfo *
0x10007fbc  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SG_NPAUFailureInfo@3@PAV123@PADI@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,uint)
0x10007fc1  test    al, al
0x10007fc3  jz      short loc_10007FC8
0x10007fc5  mov     [esi+30h], edi
0x10007fc8  mov     ebx, [ebx]
0x10007fca  mov     al, [ebx+14h]
0x10007fcd  mov     byte ptr [ebx+14h], 1
0x10007fd1  test    al, al
0x10007fd3  jnz     short loc_10007FFE
0x10007fd5  mov     edi, [ebx+4]
0x10007fd8  push    [ebp+var_8]
0x10007fdb  mov     eax, [edi]
0x10007fdd  mov     esi, [eax]
0x10007fdf  mov     ecx, esi; this
0x10007fe1  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10007fe7  mov     ecx, edi
0x10007fe9  call    esi
0x10007feb  mov     cl, [ebp+var_1]
0x10007fee  or      cl, al
0x10007ff0  mov     byte ptr [ebx+14h], 0
0x10007ff4  mov     [ebp+var_1], cl
0x10007ff7  jmp     short loc_10008001
0x10007ff9  add     ebx, 8
0x10007ffc  jmp     short loc_10007FA8
0x10007ffe  mov     cl, [ebp+var_1]
0x10008001  mov     ebx, [ebx+8]
0x10008004  test    ebx, ebx
0x10008006  jnz     short loc_10007FCA
0x10008008  mov     esi, [ebp+var_8]
0x1000800b  jmp     short loc_10008010
0x1000800d  mov     cl, [ebp+var_1]
0x10008010  mov     edi, ?g_pfnTelemetryCallback@details@wil@@3P6GX_NABUFailureInfo@2@@_EA
0x10008016  test    edi, edi
0x10008018  jz      short loc_10008037
0x1000801a  test    cl, cl
0x1000801c  jnz     short loc_10008028
0x1000801e  test    byte ptr [esi+4], 2
0x10008022  jnz     short loc_10008028
0x10008024  xor     al, al
0x10008026  jmp     short loc_1000802B
0x10008028  xor     eax, eax
0x1000802a  inc     eax
0x1000802b  push    esi
0x1000802c  push    eax
0x1000802d  mov     ecx, edi; this
0x1000802f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10008035  call    edi ; ?g_pfnTelemetryCallback@details@wil@@3P6GX_NABUFailureInfo@2@@_EA
0x10008037  pop     edi
0x10008038  pop     esi
0x10008039  pop     ebx
0x1000803a  leave
0x1000803b  retn    4
```
