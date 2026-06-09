# CActiveXInstallBroker::RegisterDllFile2ThreadProc(void *)

- ea: `0x1400055c0`
- end: `0x140005629`
- name: `?RegisterDllFile2ThreadProc@CActiveXInstallBroker@@CAKPEAX@Z`
- size: `105`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140005188`
- `0x1400055c0`

## import_xrefs

- `ole32!CoInitialize` at `0x1400055cf`
- `ole32!CoInitialize` at `0x1400055cf`
- `ole32!CoUninitialize` at `0x14000560f`
- `ole32!CoUninitialize` at `0x14000560f`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::RegisterDllFile2ThreadProc(PVOID Parameter)
{
  int v2; // edi

  v2 = CoInitialize(0);
  if ( v2 >= 0 )
  {
    if ( Parameter && *(_QWORD *)Parameter )
      v2 = CActiveXInstallBroker::RegisterDllFile2Helper(
             *(CActiveXInstallBroker **)Parameter,
             *((unsigned __int16 **)Parameter + 1),
             *((unsigned __int16 **)Parameter + 2),
             *((_DWORD *)Parameter + 6),
             *((_DWORD *)Parameter + 7));
    else
      v2 = -2147024809;
    CoUninitialize();
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400055c0  mov     [rsp+arg_0], rbx
0x1400055c5  push    rdi
0x1400055c6  sub     rsp, 30h
0x1400055ca  mov     rbx, rcx
0x1400055cd  xor     ecx, ecx; pvReserved
0x1400055cf  call    cs:__imp_CoInitialize
0x1400055d6  nop     dword ptr [rax+rax+00h]
0x1400055db  mov     edi, eax
0x1400055dd  test    eax, eax
0x1400055df  js      short loc_14000561B
0x1400055e1  test    rbx, rbx
0x1400055e4  jz      short loc_14000560A
0x1400055e6  mov     rcx, [rbx]; this
0x1400055e9  test    rcx, rcx
0x1400055ec  jz      short loc_14000560A
0x1400055ee  mov     eax, [rbx+1Ch]
0x1400055f1  mov     r9d, [rbx+18h]; int
0x1400055f5  mov     r8, [rbx+10h]; unsigned __int16 *
0x1400055f9  mov     rdx, [rbx+8]; unsigned __int16 *
0x1400055fd  mov     [rsp+38h+var_18], eax; int
0x140005601  call    ?RegisterDllFile2Helper@CActiveXInstallBroker@@AEAAJPEAG0HH@Z; CActiveXInstallBroker::RegisterDllFile2Helper(ushort *,ushort *,int,int)
0x140005606  mov     edi, eax
0x140005608  jmp     short loc_14000560F
0x14000560a  mov     edi, 80070057h
0x14000560f  call    cs:__imp_CoUninitialize
0x140005616  nop     dword ptr [rax+rax+00h]
0x14000561b  mov     rbx, [rsp+38h+arg_0]
0x140005620  mov     eax, edi
0x140005622  add     rsp, 30h
0x140005626  pop     rdi
0x140005627  retn
```
