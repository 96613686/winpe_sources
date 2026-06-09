# SessionIdProvider::CreateSessionId(void)

- ea: `0x1000784e`
- end: `0x1000791d`
- name: `?CreateSessionId@SessionIdProvider@@SG?AU_GUID@@XZ`
- size: `207`
- prototype: `struct _GUID *__stdcall(struct _GUID *__return_ptr retstr)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x100087bd`

## callees

- `0x1000784e`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x10007876`
- `KERNEL32!GetCurrentProcessId` at `0x10007876`
- `KERNEL32!GetCurrentProcess` at `0x100078af`
- `KERNEL32!GetCurrentProcess` at `0x100078af`
- `KERNEL32!GetProcessTimes` at `0x100078b6`
- `KERNEL32!GetProcessTimes` at `0x100078b6`

## pseudocode

```c
struct _GUID *__stdcall SessionIdProvider::CreateSessionId(struct _GUID *__return_ptr retstr)
{
  int v1; // ecx
  HANDLE CurrentProcess; // eax
  struct _GUID *result; // eax
  struct _FILETIME ExitTime; // [esp+8h] [ebp-20h] BYREF
  struct _FILETIME KernelTime; // [esp+10h] [ebp-18h] BYREF
  struct _FILETIME UserTime; // [esp+18h] [ebp-10h] BYREF
  struct _FILETIME CreationTime; // [esp+20h] [ebp-8h] BYREF

  v1 = 0;
  while ( *(&_GUID_00000000_0000_0000_0000_000000000000.Data1 + v1) == *(&`SessionIdProvider::CreateSessionId'::`2'::sessionId.Data1
                                                                       + v1) )
  {
    if ( ++v1 == 4 )
    {
      `SessionIdProvider::CreateSessionId'::`2'::sessionId.Data1 = GetCurrentProcessId();
      CreationTime = 0;
      *(_DWORD *)&`SessionIdProvider::CreateSessionId'::`2'::sessionId.Data2 = 0;
      ExitTime = 0;
      KernelTime = 0;
      UserTime = 0;
      CurrentProcess = GetCurrentProcess();
      if ( GetProcessTimes(CurrentProcess, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
      {
        `SessionIdProvider::CreateSessionId'::`2'::sessionId.Data4[0] = HIBYTE(CreationTime.dwHighDateTime);
        `SessionIdProvider::CreateSessionId'::`2'::sessionId.Data4[1] = BYTE2(CreationTime.dwHighDateTime);
        `SessionIdProvider::CreateSessionId'::`2'::sessionId.Data4[2] = BYTE1(CreationTime.dwHighDateTime);
        `SessionIdProvider::CreateSessionId'::`2'::sessionId.Data4[3] = CreationTime.dwHighDateTime;
        `SessionIdProvider::CreateSessionId'::`2'::sessionId.Data4[4] = HIBYTE(CreationTime.dwLowDateTime);
        `SessionIdProvider::CreateSessionId'::`2'::sessionId.Data4[5] = BYTE2(CreationTime.dwLowDateTime);
        `SessionIdProvider::CreateSessionId'::`2'::sessionId.Data4[6] = BYTE1(CreationTime.dwLowDateTime);
        `SessionIdProvider::CreateSessionId'::`2'::sessionId.Data4[7] = CreationTime.dwLowDateTime;
      }
      break;
    }
  }
  result = retstr;
  *retstr = `SessionIdProvider::CreateSessionId'::`2'::sessionId;
  return result;
}

```

## disassembly

```asm
0x1000784e  mov     edi, edi
0x10007850  push    ebp
0x10007851  mov     ebp, esp
0x10007853  sub     esp, 20h
0x10007856  mov     edx, offset __GUID_00000000_0000_0000_0000_000000000000
0x1000785b  xor     ecx, ecx
0x1000785d  push    esi
0x1000785e  push    edi
0x1000785f  mov     esi, offset ?sessionId@?1??CreateSessionId@SessionIdProvider@@SG?AU_GUID@@XZ@4U3@A; _GUID `SessionIdProvider::CreateSessionId(void)'::`2'::sessionId
0x10007864  mov     eax, [edx+ecx*4]
0x10007867  cmp     eax, [esi+ecx*4]
0x1000786a  jnz     loc_1000790E
0x10007870  inc     ecx
0x10007871  cmp     ecx, 4
0x10007874  jnz     short loc_10007864
0x10007876  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1000787c  mov     ?sessionId@?1??CreateSessionId@SessionIdProvider@@SG?AU_GUID@@XZ@4U3@A.Data1, eax; _GUID `SessionIdProvider::CreateSessionId(void)'::`2'::sessionId ...
0x10007881  xorps   xmm0, xmm0
0x10007884  xor     eax, eax
0x10007886  movlpd  qword ptr [ebp+CreationTime.dwLowDateTime], xmm0
0x1000788b  mov     dword ptr ?sessionId@?1??CreateSessionId@SessionIdProvider@@SG?AU_GUID@@XZ@4U3@A.Data2, eax; _GUID `SessionIdProvider::CreateSessionId(void)'::`2'::sessionId ...
0x10007890  lea     eax, [ebp+UserTime]
0x10007893  push    eax; lpUserTime
0x10007894  lea     eax, [ebp+KernelTime]
0x10007897  movlpd  qword ptr [ebp+ExitTime.dwLowDateTime], xmm0
0x1000789c  push    eax; lpKernelTime
0x1000789d  lea     eax, [ebp+ExitTime]
0x100078a0  movlpd  qword ptr [ebp+KernelTime.dwLowDateTime], xmm0
0x100078a5  push    eax; lpExitTime
0x100078a6  lea     eax, [ebp+CreationTime]
0x100078a9  movlpd  qword ptr [ebp+UserTime.dwLowDateTime], xmm0
0x100078ae  push    eax; lpCreationTime
0x100078af  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x100078b5  push    eax; hProcess
0x100078b6  call    ds:__imp__GetProcessTimes@20; GetProcessTimes(x,x,x,x,x)
0x100078bc  test    eax, eax
0x100078be  jz      short loc_1000790E
0x100078c0  mov     ecx, [ebp+CreationTime.dwHighDateTime]
0x100078c3  mov     eax, ecx
0x100078c5  shr     eax, 18h
0x100078c8  mov     ?sessionId@?1??CreateSessionId@SessionIdProvider@@SG?AU_GUID@@XZ@4U3@A.Data4, al; _GUID `SessionIdProvider::CreateSessionId(void)'::`2'::sessionId ...
0x100078cd  mov     eax, ecx
0x100078cf  shr     eax, 10h
0x100078d2  mov     ?sessionId@?1??CreateSessionId@SessionIdProvider@@SG?AU_GUID@@XZ@4U3@A.Data4+1, al; _GUID `SessionIdProvider::CreateSessionId(void)'::`2'::sessionId ...
0x100078d7  mov     eax, ecx
0x100078d9  shr     eax, 8
0x100078dc  mov     ?sessionId@?1??CreateSessionId@SessionIdProvider@@SG?AU_GUID@@XZ@4U3@A.Data4+2, al; _GUID `SessionIdProvider::CreateSessionId(void)'::`2'::sessionId ...
0x100078e1  mov     ?sessionId@?1??CreateSessionId@SessionIdProvider@@SG?AU_GUID@@XZ@4U3@A.Data4+3, cl; _GUID `SessionIdProvider::CreateSessionId(void)'::`2'::sessionId ...
0x100078e7  mov     ecx, [ebp+CreationTime.dwLowDateTime]
0x100078ea  mov     eax, ecx
0x100078ec  shr     eax, 18h
0x100078ef  mov     ?sessionId@?1??CreateSessionId@SessionIdProvider@@SG?AU_GUID@@XZ@4U3@A.Data4+4, al; _GUID `SessionIdProvider::CreateSessionId(void)'::`2'::sessionId ...
0x100078f4  mov     eax, ecx
0x100078f6  shr     eax, 10h
0x100078f9  mov     ?sessionId@?1??CreateSessionId@SessionIdProvider@@SG?AU_GUID@@XZ@4U3@A.Data4+5, al; _GUID `SessionIdProvider::CreateSessionId(void)'::`2'::sessionId ...
0x100078fe  mov     eax, ecx
0x10007900  shr     eax, 8
0x10007903  mov     ?sessionId@?1??CreateSessionId@SessionIdProvider@@SG?AU_GUID@@XZ@4U3@A.Data4+6, al; _GUID `SessionIdProvider::CreateSessionId(void)'::`2'::sessionId ...
0x10007908  mov     ?sessionId@?1??CreateSessionId@SessionIdProvider@@SG?AU_GUID@@XZ@4U3@A.Data4+7, cl; _GUID `SessionIdProvider::CreateSessionId(void)'::`2'::sessionId ...
0x1000790e  mov     eax, [ebp+retstr]
0x10007911  mov     edi, eax
0x10007913  movsd
0x10007914  movsd
0x10007915  movsd
0x10007916  movsd
0x10007917  pop     edi
0x10007918  pop     esi
0x10007919  leave
0x1000791a  retn    4
```
