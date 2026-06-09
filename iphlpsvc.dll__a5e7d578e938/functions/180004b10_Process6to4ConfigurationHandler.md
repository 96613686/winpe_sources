# Process6to4ConfigurationHandler

- ea: `0x180004b10`
- end: `0x180004c5b`
- name: `Process6to4ConfigurationHandler`
- size: `331`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180004b10`
- `0x180004c64`
- `0x180004f60`
- `0x18000d7c0`
- `0x18002a19c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004be0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004be0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004c4d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004c4d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004b82`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004b82`

## string_xrefs

- `0x180004c34`: `Process6to4ConfigurationChange`
- `0x180004b4a`: `Process6to4ConfigurationHandler`
- `0x180004bb3`: `Process6to4ConfigurationHandler`
- `0x180004c2d`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180004b57`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180004b9a`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180004bf0`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`

## pseudocode

```c
__int64 __fastcall Process6to4ConfigurationHandler(__int64 a1)
{
  void *v1; // rbp
  HANDLE v3; // rdi
  DWORD v4; // eax
  const wchar_t *v5; // rdx
  DWORD v6; // ebx
  HANDLE v7; // rbx
  __int64 v9; // [rsp+28h] [rbp-40h]
  __int64 v10; // [rsp+28h] [rbp-40h]
  __int64 v11; // [rsp+30h] [rbp-38h]

  v1 = 0;
  if ( *(_QWORD *)(a1 + 40) )
    v1 = *(void **)(a1 + 40);
  if ( !g_StopServiceEventSet && dword_1800C9754 )
  {
    v3 = g_6to4Lock;
    EventWrite0(
      0x800000,
      L"Get lock (%p) invoked at %S : %S : %u",
      g_6to4Lock,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
      "Process6to4ConfigurationHandler",
      920);
    v4 = WaitForSingleObject(v3, 0xFFFFFFFF);
    v5 = L"Lock (%p) acquired at %S : %S : %u. Return %d";
    v6 = v4;
    LODWORD(v9) = 920;
    if ( v4 )
      v5 = L"Lock (%p) failed at %S : %S : %u. Return %d";
    EventWrite0(
      0x800000,
      v5,
      v3,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
      "Process6to4ConfigurationHandler",
      v9,
      v4);
    if ( !v6 )
    {
      Process6to4ConfigurationChangeUnderLock();
      v7 = g_6to4Lock;
      LODWORD(v11) = ReleaseMutex(g_6to4Lock);
      LODWORD(v10) = 926;
      EventWrite0(
        0x800000,
        L"Lock (%p) released at %S : %S : %u. Return %d",
        v7,
        "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
        "Process6to4ConfigurationHandler",
        v10,
        v11);
    }
  }
  if ( *(_QWORD *)(a1 + 40) )
    SetEvent(v1);
  FREE(a1);
  return DereferenceServiceEx(
           "Process6to4ConfigurationChange",
           L"onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
           935);
}

```

## disassembly

```asm
0x180004b10  push    rbx
0x180004b12  push    rbp
0x180004b13  push    rsi
0x180004b14  push    rdi
0x180004b15  push    r14
0x180004b17  sub     rsp, 40h
0x180004b1b  xor     ebp, ebp
0x180004b1d  mov     rsi, rcx
0x180004b20  cmp     [rcx+28h], rbp
0x180004b24  cmovnz  rbp, [rcx+28h]
0x180004b29  cmp     cs:g_StopServiceEventSet, 0
0x180004b30  jnz     loc_180004C18
0x180004b36  cmp     cs:dword_1800C9754, 0
0x180004b3d  jz      loc_180004C18
0x180004b43  mov     rdi, cs:g_6to4Lock
0x180004b4a  lea     rax, aProcess6to4con_0; "Process6to4ConfigurationHandler"
0x180004b51  mov     r14d, 398h
0x180004b57  lea     r9, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180004b5e  mov     dword ptr [rsp+68h+var_40], r14d
0x180004b63  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x180004b6a  mov     r8, rdi
0x180004b6d  mov     [rsp+68h+var_48], rax
0x180004b72  mov     ecx, 800000h
0x180004b77  call    EventWrite0
0x180004b7c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004b7f  mov     rcx, rdi; hHandle
0x180004b82  call    cs:__imp_WaitForSingleObject
0x180004b89  nop     dword ptr [rax+rax+00h]
0x180004b8e  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x180004b95  mov     r8, rdi
0x180004b98  mov     ebx, eax
0x180004b9a  lea     r9, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180004ba1  mov     dword ptr [rsp+68h+var_38], ebx
0x180004ba5  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x180004bac  mov     dword ptr [rsp+68h+var_40], r14d
0x180004bb1  test    ebx, ebx
0x180004bb3  lea     r14, aProcess6to4con_0; "Process6to4ConfigurationHandler"
0x180004bba  mov     ecx, 800000h
0x180004bbf  cmovnz  rdx, rax
0x180004bc3  mov     [rsp+68h+var_48], r14
0x180004bc8  call    EventWrite0
0x180004bcd  test    ebx, ebx
0x180004bcf  jnz     short loc_180004C18
0x180004bd1  call    Process6to4ConfigurationChangeUnderLock
0x180004bd6  mov     rbx, cs:g_6to4Lock
0x180004bdd  mov     rcx, rbx; hMutex
0x180004be0  call    cs:__imp_ReleaseMutex
0x180004be7  nop     dword ptr [rax+rax+00h]
0x180004bec  mov     dword ptr [rsp+68h+var_38], eax
0x180004bf0  lea     r9, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180004bf7  mov     dword ptr [rsp+68h+var_40], 39Eh
0x180004bff  mov     r8, rbx
0x180004c02  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x180004c09  mov     [rsp+68h+var_48], r14
0x180004c0e  mov     ecx, 800000h
0x180004c13  call    EventWrite0
0x180004c18  cmp     qword ptr [rsi+28h], 0
0x180004c1d  jnz     short loc_180004C4A
0x180004c1f  mov     rcx, rsi
0x180004c22  call    FREE
0x180004c27  mov     r8d, 3A7h
0x180004c2d  lea     rdx, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180004c34  lea     rcx, aProcess6to4con; "Process6to4ConfigurationChange"
0x180004c3b  add     rsp, 40h
0x180004c3f  pop     r14
0x180004c41  pop     rdi
0x180004c42  pop     rsi
0x180004c43  pop     rbp
0x180004c44  pop     rbx
0x180004c45  jmp     DereferenceServiceEx
0x180004c4a  mov     rcx, rbp; hEvent
0x180004c4d  call    cs:__imp_SetEvent
0x180004c54  nop     dword ptr [rax+rax+00h]
0x180004c59  jmp     short loc_180004C1F
```
