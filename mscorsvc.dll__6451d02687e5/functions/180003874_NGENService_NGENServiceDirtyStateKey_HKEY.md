# NGENService::NGENServiceDirtyStateKey(HKEY__ * *)

- ea: `0x180003874`
- end: `0x1800039ab`
- name: `?NGENServiceDirtyStateKey@NGENService@@YAJPEAPEAUHKEY__@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(HKEY *this, HKEY *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003c90`
- `0x1800046c4`

## callees

- `0x180001e8c`
- `0x180003874`
- `0x1800068a8`
- `0x180030d84`
- `0x180037964`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000397b`
- `KERNEL32!HeapFree` at `0x18000397b`
- `KERNEL32!GetProcessHeap` at `0x180003966`
- `KERNEL32!GetProcessHeap` at `0x180003966`

## string_xrefs

- `0x1800038df`: `\NgenService`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NGENService::NGENServiceDirtyStateKey(HKEY *this, HKEY *a2)
{
  __int64 v3; // r8
  unsigned __int16 *v4; // r9
  LSTATUS Key; // eax
  unsigned int v6; // ebx
  void *v7; // rdi
  HANDLE ProcessHeap; // rax
  struct _SECURITY_ATTRIBUTES *v10; // [rsp+38h] [rbp-D0h]
  int v11; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v12; // [rsp+5Ch] [rbp-ACh]
  LPVOID lpMem; // [rsp+68h] [rbp-A0h]
  __int16 v14; // [rsp+70h] [rbp-98h] BYREF

  v12 = 512;
  lpMem = &v14;
  v11 = 2;
  v14 = 0;
  Helpers::CLRVersionRegistryRootName((struct SString *)&v11);
  SString::Append((SString *)&v11, L"\\NgenService");
  SString::Append((SString *)&v11, L"\\ListenedState");
  SString::ConvertToUnicode((SString *)&v11);
  Key = ClrRegCreateKeyEx(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)lpMem, v3, v4, 0, 0x2001Fu, v10, this);
  if ( Key )
    v6 = (Key != 0) | 0x80070000;
  else
    v6 = 0;
  if ( (v12 & 0x800000000LL) != 0 )
  {
    v7 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v7);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180003874  mov     rax, rsp
0x180003877  mov     [rax+10h], rbx
0x18000387b  mov     [rax+18h], rsi
0x18000387f  mov     [rax+20h], rdi
0x180003883  push    rbp
0x180003884  lea     rbp, [rax-188h]
0x18000388b  sub     rsp, 280h
0x180003892  mov     rax, cs:__security_cookie
0x180003899  xor     rax, rsp
0x18000389c  mov     [rbp+180h+var_10], rax
0x1800038a3  mov     rbx, rcx
0x1800038a6  xor     esi, esi
0x1800038a8  mov     qword ptr [rsp+280h+var_230], rsi
0x1800038ad  mov     qword ptr [rsp+54h], 200h
0x1800038b6  mov     [rsp+280h+lpMem], rsi
0x1800038bb  lea     rax, [rsp+280h+var_218]
0x1800038c0  mov     [rsp+280h+lpMem], rax
0x1800038c5  mov     [rsp+280h+var_230], 2
0x1800038cd  mov     rax, [rsp+280h+lpMem]
0x1800038d2  mov     [rax], si
0x1800038d5  lea     rcx, [rsp+280h+var_230]; this
0x1800038da  call    ?CLRVersionRegistryRootName@Helpers@@SAXAEAVSString@@@Z
0x1800038df  lea     rdx, aNgenservice_0
0x1800038e6  lea     rcx, [rsp+280h+var_230]; this
0x1800038eb  call    ?Append@SString@@QEAAXPEBG@Z
0x1800038f0  lea     rdx, aListenedstate
0x1800038f7  lea     rcx, [rsp+280h+var_230]; this
0x1800038fc  call    ?Append@SString@@QEAAXPEBG@Z
0x180003901  lea     rcx, [rsp+280h+var_230]; this
0x180003906  call    ?ConvertToUnicode@SString@@AEBAXXZ
0x18000390b  mov     [rsp+280h+var_248], rbx; HKEY *
0x180003910  mov     [rsp+280h+var_258], 2001Fh; REGSAM
0x180003918  mov     [rsp+280h+var_260], esi; DWORD
0x18000391c  mov     rdx, [rsp+280h+lpMem]; unsigned __int16 *
0x180003921  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180003928  call    ?ClrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z
0x18000392d  mov     ecx, esi
0x18000392f  test    eax, eax
0x180003931  setnz   cl
0x180003934  test    eax, eax
0x180003936  jz      short loc_180003947
0x180003938  mov     ebx, ecx
0x18000393a  or      ebx, 80070000h
0x180003940  test    ecx, ecx
0x180003942  cmovz   ebx, ecx
0x180003945  jmp     short loc_180003949
0x180003947  mov     ebx, esi
0x180003949  test    byte ptr [rsp+280h+var_228], 8
0x18000394e  jz      short loc_180003981
0x180003950  mov     rdi, [rsp+280h+lpMem]
0x180003955  test    rdi, rdi
0x180003958  jz      short loc_180003981
0x18000395a  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA
0x180003961  test    rax, rax
0x180003964  jnz     short loc_180003973
0x180003966  call    cs:__imp_GetProcessHeap
0x18000396c  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax
0x180003973  mov     r8, rdi; lpMem
0x180003976  xor     edx, edx; dwFlags
0x180003978  mov     rcx, rax; hHeap
0x18000397b  call    cs:__imp_HeapFree
0x180003981  mov     eax, ebx
0x180003983  mov     rcx, [rbp+180h+var_10]
0x18000398a  xor     rcx, rsp; StackCookie
0x18000398d  call    __security_check_cookie
0x180003992  lea     r11, [rsp+280h+var_s0]
0x18000399a  mov     rbx, [r11+18h]
0x18000399e  mov     rsi, [r11+20h]
0x1800039a2  mov     rdi, [r11+28h]
0x1800039a6  mov     rsp, r11
0x1800039a9  pop     rbp
0x1800039aa  retn
```
