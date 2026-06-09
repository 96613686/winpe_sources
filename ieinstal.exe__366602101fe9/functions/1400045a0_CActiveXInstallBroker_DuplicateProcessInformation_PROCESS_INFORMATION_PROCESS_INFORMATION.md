# CActiveXInstallBroker::DuplicateProcessInformation(_PROCESS_INFORMATION *,_PROCESS_INFORMATION *)

- ea: `0x1400045a0`
- end: `0x140004732`
- name: `?DuplicateProcessInformation@CActiveXInstallBroker@@AEAAJPEAU_PROCESS_INFORMATION@@0@Z`
- size: `402`
- prototype: `__int64 __fastcall(CActiveXInstallBroker *__hidden this, struct _PROCESS_INFORMATION *, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140005630`

## callees

- `0x1400045a0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400046dc`
- `KERNEL32!CloseHandle` at `0x1400046f2`
- `KERNEL32!CloseHandle` at `0x140004706`
- `KERNEL32!CloseHandle` at `0x1400046dc`
- `KERNEL32!CloseHandle` at `0x1400046f2`
- `KERNEL32!CloseHandle` at `0x140004706`
- `KERNEL32!GetCurrentProcess` at `0x1400045ba`
- `KERNEL32!GetCurrentProcess` at `0x1400045ba`
- `KERNEL32!OpenProcess` at `0x140004602`
- `KERNEL32!OpenProcess` at `0x140004602`
- `KERNEL32!DuplicateHandle` at `0x140004640`
- `KERNEL32!DuplicateHandle` at `0x14000467a`
- `KERNEL32!DuplicateHandle` at `0x140004640`
- `KERNEL32!DuplicateHandle` at `0x14000467a`
- `KERNEL32!GetLastError` at `0x1400046b4`
- `KERNEL32!GetLastError` at `0x1400046b4`
- `ole32!CoImpersonateClient` at `0x1400045de`
- `ole32!CoImpersonateClient` at `0x1400045de`
- `ole32!CoRevertToSelf` at `0x140004716`
- `ole32!CoRevertToSelf` at `0x140004716`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::DuplicateProcessInformation(
        CActiveXInstallBroker *this,
        struct _PROCESS_INFORMATION *a2,
        struct _PROCESS_INFORMATION *a3)
{
  int v6; // ebx
  int v7; // esi
  HANDLE CurrentProcess; // rbp
  HANDLE v9; // rax
  void *v10; // rdi
  signed int LastError; // eax
  HANDLE TargetHandle; // [rsp+40h] [rbp-48h] BYREF
  HANDLE hObject; // [rsp+A8h] [rbp+20h] BYREF

  v6 = 0;
  v7 = 0;
  CurrentProcess = GetCurrentProcess();
  TargetHandle = 0;
  hObject = 0;
  if ( !g_fRunningAsSystem )
  {
    v6 = CoImpersonateClient();
    if ( v6 < 0 )
    {
      v10 = 0;
      goto LABEL_11;
    }
    v7 = 1;
  }
  v9 = OpenProcess(0x40u, 0, *((_DWORD *)this + 30));
  v10 = v9;
  if ( v9
    && DuplicateHandle(CurrentProcess, a2->hProcess, v9, &TargetHandle, 0x20000100u, 0, 0)
    && DuplicateHandle(CurrentProcess, a2->hThread, v10, &hObject, 0x20000002u, 0, 0) )
  {
    a3->hProcess = TargetHandle;
    a3->hThread = hObject;
    a3->dwProcessId = a2->dwProcessId;
    a3->dwThreadId = a2->dwThreadId;
LABEL_16:
    CloseHandle(v10);
    goto LABEL_17;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_11:
  if ( hObject )
    CloseHandle(hObject);
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  if ( v10 )
    goto LABEL_16;
LABEL_17:
  if ( v7 )
    CoRevertToSelf();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400045a0  push    rbx
0x1400045a2  push    rbp
0x1400045a3  push    rsi
0x1400045a4  push    rdi
0x1400045a5  push    r14
0x1400045a7  push    r15
0x1400045a9  sub     rsp, 58h
0x1400045ad  mov     r14, r8
0x1400045b0  mov     r15, rdx
0x1400045b3  mov     rdi, rcx
0x1400045b6  xor     ebx, ebx
0x1400045b8  xor     esi, esi
0x1400045ba  call    cs:__imp_GetCurrentProcess
0x1400045c1  nop     dword ptr [rax+rax+00h]
0x1400045c6  cmp     cs:?g_fRunningAsSystem@@3HA, ebx; int g_fRunningAsSystem
0x1400045cc  mov     rbp, rax
0x1400045cf  mov     [rsp+88h+TargetHandle], rbx
0x1400045d4  mov     [rsp+88h+hObject], rbx
0x1400045dc  jnz     short loc_1400045F9
0x1400045de  call    cs:__imp_CoImpersonateClient
0x1400045e5  nop     dword ptr [rax+rax+00h]
0x1400045ea  mov     ebx, eax
0x1400045ec  test    eax, eax
0x1400045ee  js      loc_1400046B0
0x1400045f4  mov     esi, 1
0x1400045f9  mov     r8d, [rdi+78h]; dwProcessId
0x1400045fd  xor     edx, edx; bInheritHandle
0x1400045ff  lea     ecx, [rdx+40h]; dwDesiredAccess
0x140004602  call    cs:__imp_OpenProcess
0x140004609  nop     dword ptr [rax+rax+00h]
0x14000460e  mov     rdi, rax
0x140004611  test    rax, rax
0x140004614  jz      loc_1400046B4
0x14000461a  mov     rdx, [r15]; hSourceHandle
0x14000461d  lea     r9, [rsp+88h+TargetHandle]; lpTargetHandle
0x140004622  mov     [rsp+88h+dwOptions], 0; dwOptions
0x14000462a  mov     r8, rax; hTargetProcessHandle
0x14000462d  mov     [rsp+88h+bInheritHandle], 0; bInheritHandle
0x140004635  mov     rcx, rbp; hSourceProcessHandle
0x140004638  mov     [rsp+88h+dwDesiredAccess], 20000100h; dwDesiredAccess
0x140004640  call    cs:__imp_DuplicateHandle
0x140004647  nop     dword ptr [rax+rax+00h]
0x14000464c  test    eax, eax
0x14000464e  jz      short loc_1400046B4
0x140004650  mov     rdx, [r15+8]; hSourceHandle
0x140004654  lea     r9, [rsp+88h+hObject]; lpTargetHandle
0x14000465c  mov     [rsp+88h+dwOptions], 0; dwOptions
0x140004664  mov     r8, rdi; hTargetProcessHandle
0x140004667  mov     [rsp+88h+bInheritHandle], 0; bInheritHandle
0x14000466f  mov     rcx, rbp; hSourceProcessHandle
0x140004672  mov     [rsp+88h+dwDesiredAccess], 20000002h; dwDesiredAccess
0x14000467a  call    cs:__imp_DuplicateHandle
0x140004681  nop     dword ptr [rax+rax+00h]
0x140004686  test    eax, eax
0x140004688  jz      short loc_1400046B4
0x14000468a  mov     rax, [rsp+88h+TargetHandle]
0x14000468f  mov     [r14], rax
0x140004692  mov     rax, [rsp+88h+hObject]
0x14000469a  mov     [r14+8], rax
0x14000469e  mov     eax, [r15+10h]
0x1400046a2  mov     [r14+10h], eax
0x1400046a6  mov     eax, [r15+14h]
0x1400046aa  mov     [r14+14h], eax
0x1400046ae  jmp     short loc_140004703
0x1400046b0  xor     edi, edi
0x1400046b2  jmp     short loc_1400046CF
0x1400046b4  call    cs:__imp_GetLastError
0x1400046bb  nop     dword ptr [rax+rax+00h]
0x1400046c0  mov     ebx, eax
0x1400046c2  test    eax, eax
0x1400046c4  jle     short loc_1400046CF
0x1400046c6  movzx   ebx, ax
0x1400046c9  or      ebx, 80070000h
0x1400046cf  mov     rcx, [rsp+88h+hObject]; hObject
0x1400046d7  test    rcx, rcx
0x1400046da  jz      short loc_1400046E8
0x1400046dc  call    cs:__imp_CloseHandle
0x1400046e3  nop     dword ptr [rax+rax+00h]
0x1400046e8  mov     rcx, [rsp+88h+TargetHandle]; hObject
0x1400046ed  test    rcx, rcx
0x1400046f0  jz      short loc_1400046FE
0x1400046f2  call    cs:__imp_CloseHandle
0x1400046f9  nop     dword ptr [rax+rax+00h]
0x1400046fe  test    rdi, rdi
0x140004701  jz      short loc_140004712
0x140004703  mov     rcx, rdi; hObject
0x140004706  call    cs:__imp_CloseHandle
0x14000470d  nop     dword ptr [rax+rax+00h]
0x140004712  test    esi, esi
0x140004714  jz      short loc_140004722
0x140004716  call    cs:__imp_CoRevertToSelf
0x14000471d  nop     dword ptr [rax+rax+00h]
0x140004722  mov     eax, ebx
0x140004724  add     rsp, 58h
0x140004728  pop     r15
0x14000472a  pop     r14
0x14000472c  pop     rdi
0x14000472d  pop     rsi
0x14000472e  pop     rbp
0x14000472f  pop     rbx
0x140004730  retn
```
