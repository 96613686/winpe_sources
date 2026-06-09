# CActiveXInstallBroker::~CActiveXInstallBroker(void)

- ea: `0x14000447c`
- end: `0x1400044b9`
- name: `??1CActiveXInstallBroker@@QEAA@XZ`
- size: `61`
- prototype: `void __fastcall(CActiveXInstallBroker *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140007bcc`
- `0x140007e20`
- `0x140007ed0`

## callees

- `0x14000447c`
- `0x1400059f0`
- `0x14000abd4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400044a6`
- `KERNEL32!DeleteCriticalSection` at `0x1400044a6`

## pseudocode

```c
void __fastcall CActiveXInstallBroker::~CActiveXInstallBroker(CActiveXInstallBroker *this)
{
  CActiveXInstallBroker::Reset((BSTR *)this, 0);
  if ( *((_BYTE *)this + 160) )
    RemoveDirectoryAndChildren((const char *)this + 160);
  if ( *(_DWORD *)this )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x14000447c  push    rbx
0x14000447e  sub     rsp, 20h
0x140004482  xor     edx, edx; int
0x140004484  mov     rbx, rcx
0x140004487  call    ?Reset@CActiveXInstallBroker@@AEAAXH@Z; CActiveXInstallBroker::Reset(int)
0x14000448c  lea     rcx, [rbx+0A0h]; char *
0x140004493  cmp     byte ptr [rcx], 0
0x140004496  jz      short loc_14000449D
0x140004498  call    ?RemoveDirectoryAndChildren@@YAJPEBD@Z; RemoveDirectoryAndChildren(char const *)
0x14000449d  cmp     dword ptr [rbx], 0
0x1400044a0  jz      short loc_1400044B2
0x1400044a2  lea     rcx, [rbx+8]; lpCriticalSection
0x1400044a6  call    cs:__imp_DeleteCriticalSection
0x1400044ad  nop     dword ptr [rax+rax+00h]
0x1400044b2  add     rsp, 20h
0x1400044b6  pop     rbx
0x1400044b7  retn
```
