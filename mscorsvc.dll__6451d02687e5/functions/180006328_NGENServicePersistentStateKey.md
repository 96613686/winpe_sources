# NGENServicePersistentStateKey

- ea: `0x180006328`
- end: `0x18000645f`
- name: `NGENServicePersistentStateKey`
- size: `311`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003a54`
- `0x1800046c4`

## callees

- `0x180001e8c`
- `0x180006328`
- `0x1800068a8`
- `0x180030d84`
- `0x180037964`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000642f`
- `KERNEL32!HeapFree` at `0x18000642f`
- `KERNEL32!GetProcessHeap` at `0x18000641a`
- `KERNEL32!GetProcessHeap` at `0x18000641a`

## string_xrefs

- `0x180006393`: `\NgenService`

## pseudocode

```c
__int64 __fastcall NGENServicePersistentStateKey(HKEY *a1)
{
  __int64 v2; // r8
  unsigned __int16 *v3; // r9
  LSTATUS Key; // eax
  unsigned int v5; // ebx
  void *v6; // rdi
  HANDLE ProcessHeap; // rax
  struct _SECURITY_ATTRIBUTES *v9; // [rsp+38h] [rbp-D0h]
  int v10; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+5Ch] [rbp-ACh]
  LPVOID lpMem; // [rsp+68h] [rbp-A0h]
  __int16 v13; // [rsp+70h] [rbp-98h] BYREF

  v11 = 512;
  lpMem = &v13;
  v10 = 2;
  v13 = 0;
  Helpers::CLRVersionRegistryRootName((struct SString *)&v10);
  SString::Append((SString *)&v10, L"\\NgenService");
  SString::Append((SString *)&v10, L"\\State");
  SString::ConvertToUnicode((SString *)&v10);
  Key = ClrRegCreateKeyEx(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)lpMem, v2, v3, 0, 0x2001Fu, v9, a1);
  if ( Key )
    v5 = (Key != 0) | 0x80070000;
  else
    v5 = 0;
  if ( (v11 & 0x800000000LL) != 0 )
  {
    v6 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v6);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180006328  mov     rax, rsp
0x18000632b  mov     [rax+10h], rbx
0x18000632f  mov     [rax+18h], rsi
0x180006333  mov     [rax+20h], rdi
0x180006337  push    rbp
0x180006338  lea     rbp, [rax-188h]
0x18000633f  sub     rsp, 280h
0x180006346  mov     rax, cs:__security_cookie
0x18000634d  xor     rax, rsp
0x180006350  mov     [rbp+180h+var_10], rax
0x180006357  mov     rbx, rcx
0x18000635a  xor     esi, esi
0x18000635c  mov     qword ptr [rsp+280h+var_230], rsi
0x180006361  mov     qword ptr [rsp+54h], 200h
0x18000636a  mov     [rsp+280h+lpMem], rsi
0x18000636f  lea     rax, [rsp+280h+var_218]
0x180006374  mov     [rsp+280h+lpMem], rax
0x180006379  mov     [rsp+280h+var_230], 2
0x180006381  mov     rax, [rsp+280h+lpMem]
0x180006386  mov     [rax], si
0x180006389  lea     rcx, [rsp+280h+var_230]; this
0x18000638e  call    ?CLRVersionRegistryRootName@Helpers@@SAXAEAVSString@@@Z
0x180006393  lea     rdx, aNgenservice_0
0x18000639a  lea     rcx, [rsp+280h+var_230]; this
0x18000639f  call    ?Append@SString@@QEAAXPEBG@Z
0x1800063a4  lea     rdx, aState
0x1800063ab  lea     rcx, [rsp+280h+var_230]; this
0x1800063b0  call    ?Append@SString@@QEAAXPEBG@Z
0x1800063b5  lea     rcx, [rsp+280h+var_230]; this
0x1800063ba  call    ?ConvertToUnicode@SString@@AEBAXXZ
0x1800063bf  mov     [rsp+280h+var_248], rbx; HKEY *
0x1800063c4  mov     [rsp+280h+var_258], 2001Fh; REGSAM
0x1800063cc  mov     [rsp+280h+var_260], esi; DWORD
0x1800063d0  mov     rdx, [rsp+280h+lpMem]; unsigned __int16 *
0x1800063d5  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800063dc  call    ?ClrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z
0x1800063e1  mov     ecx, esi
0x1800063e3  test    eax, eax
0x1800063e5  setnz   cl
0x1800063e8  test    eax, eax
0x1800063ea  jz      short loc_1800063FB
0x1800063ec  mov     ebx, ecx
0x1800063ee  or      ebx, 80070000h
0x1800063f4  test    ecx, ecx
0x1800063f6  cmovz   ebx, ecx
0x1800063f9  jmp     short loc_1800063FD
0x1800063fb  mov     ebx, esi
0x1800063fd  test    byte ptr [rsp+280h+var_228], 8
0x180006402  jz      short loc_180006435
0x180006404  mov     rdi, [rsp+280h+lpMem]
0x180006409  test    rdi, rdi
0x18000640c  jz      short loc_180006435
0x18000640e  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA
0x180006415  test    rax, rax
0x180006418  jnz     short loc_180006427
0x18000641a  call    cs:__imp_GetProcessHeap
0x180006420  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax
0x180006427  mov     r8, rdi; lpMem
0x18000642a  xor     edx, edx; dwFlags
0x18000642c  mov     rcx, rax; hHeap
0x18000642f  call    cs:__imp_HeapFree
0x180006435  mov     eax, ebx
0x180006437  mov     rcx, [rbp+180h+var_10]
0x18000643e  xor     rcx, rsp; StackCookie
0x180006441  call    __security_check_cookie
0x180006446  lea     r11, [rsp+280h+var_s0]
0x18000644e  mov     rbx, [r11+18h]
0x180006452  mov     rsi, [r11+20h]
0x180006456  mov     rdi, [r11+28h]
0x18000645a  mov     rsp, r11
0x18000645d  pop     rbp
0x18000645e  retn
```
