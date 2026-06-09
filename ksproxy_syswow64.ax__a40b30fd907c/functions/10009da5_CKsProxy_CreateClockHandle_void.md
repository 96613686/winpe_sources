# CKsProxy::CreateClockHandle(void)

- ea: `0x10009da5`
- end: `0x10009e1c`
- name: `?CreateClockHandle@CKsProxy@@QAGJXZ`
- size: `119`
- prototype: `int __usercall@<eax>(int@<ecx>, CKsProxy *@<edi>, CKsProxy *this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x10009aa0`
- `0x1000b860`
- `0x1000b910`
- `0x1000ba10`
- `0x1000e356`

## callees

- `0x10009da5`
- `0x1000adfd`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x10009ddf`
- `KERNEL32!CloseHandle` at `0x10009ddf`
- `ksuser!KsCreateClock` at `0x10009df1`
- `ksuser!KsCreateClock` at `0x10009df1`

## pseudocode

```c
int __usercall CKsProxy::CreateClockHandle@<eax>(int a1@<ecx>, CKsProxy *a2@<edi>, CKsProxy *this)
{
  void *PinHandle; // edi
  HANDLE *v6; // esi
  signed int v7; // eax
  signed int v8; // ecx
  struct CBasePin *v9; // [esp+0h] [ebp-8h]
  $9CC657B7E0AE245246966219C61A944E ClockCreate; // [esp+4h] [ebp-4h] BYREF

  if ( !*(_DWORD *)(a1 + 284) )
    return -2147467263;
  PinHandle = CKsProxy::GetPinHandle(a2, v9);
  if ( !PinHandle )
    return -2147467263;
  v6 = (HANDLE *)(a1 + 228);
  ClockCreate.CreateFlags = 0;
  if ( *v6 )
  {
    CloseHandle(*v6);
    *v6 = 0;
  }
  v7 = KsCreateClock(PinHandle, &ClockCreate, v6);
  v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v7 <= 0 )
    v8 = v7;
  if ( v8 < 0 )
    *v6 = 0;
  return v8;
}

```

## disassembly

```asm
0x10009da5  mov     edi, edi
0x10009da7  push    ebp
0x10009da8  mov     ebp, esp
0x10009daa  push    ecx
0x10009dab  push    esi; struct CBasePin *
0x10009dac  mov     esi, ecx
0x10009dae  mov     edx, [esi+11Ch]
0x10009db4  test    edx, edx
0x10009db6  jnz     short loc_10009DBF
0x10009db8  mov     eax, 80004001h
0x10009dbd  jmp     short loc_10009E19
0x10009dbf  push    edi; this
0x10009dc0  call    ?GetPinHandle@CKsProxy@@QAGPAXPAVCBasePin@@@Z; CKsProxy::GetPinHandle(CBasePin *)
0x10009dc5  mov     edi, eax
0x10009dc7  test    edi, edi
0x10009dc9  jz      short loc_10009E11
0x10009dcb  add     esi, 0E4h
0x10009dd1  mov     [ebp+ClockCreate.CreateFlags], 0
0x10009dd8  cmp     dword ptr [esi], 0
0x10009ddb  jz      short loc_10009DEB
0x10009ddd  push    dword ptr [esi]; hObject
0x10009ddf  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10009de5  mov     dword ptr [esi], 0
0x10009deb  push    esi; ClockHandle
0x10009dec  lea     eax, [ebp+ClockCreate]
0x10009def  push    eax; ClockCreate
0x10009df0  push    edi; ConnectionHandle
0x10009df1  call    ds:__imp__KsCreateClock@12; KsCreateClock(x,x,x)
0x10009df7  movzx   ecx, ax
0x10009dfa  or      ecx, 80070000h
0x10009e00  test    eax, eax
0x10009e02  cmovle  ecx, eax
0x10009e05  test    ecx, ecx
0x10009e07  jns     short loc_10009E16
0x10009e09  mov     dword ptr [esi], 0
0x10009e0f  jmp     short loc_10009E16
0x10009e11  mov     ecx, 80004001h
0x10009e16  mov     eax, ecx
0x10009e18  pop     edi
0x10009e19  pop     esi
0x10009e1a  leave
0x10009e1b  retn
```
