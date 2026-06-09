# LoadWSAPoll(int (**)(pollfd * const,ulong,int),HINSTANCE__ * *)

- ea: `0x1004354b4`
- end: `0x10043571a`
- name: `?LoadWSAPoll@@YAKPEAP6AHQEAUpollfd@@KH@ZPEAPEAUHINSTANCE__@@@Z`
- size: `614`
- prototype: `unsigned int __fastcall(int (**)(struct pollfd *const, unsigned int, int), HINSTANCE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x100434d74`

## callees

- `0x100417768`
- `0x1004354b4`
- `0x10043a7c4`
- `0x10043a930`
- `0x100545d84`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100435548`
- `KERNEL32!GetLastError` at `0x1004355e4`
- `KERNEL32!GetLastError` at `0x100435681`
- `KERNEL32!GetLastError` at `0x100435548`
- `KERNEL32!GetLastError` at `0x1004355e4`
- `KERNEL32!GetLastError` at `0x100435681`
- `KERNEL32!GetProcAddress` at `0x1004355d1`
- `KERNEL32!GetProcAddress` at `0x1004355d1`
- `KERNEL32!FreeLibrary` at `0x100435677`
- `KERNEL32!FreeLibrary` at `0x100435677`

## string_xrefs

- `0x100435534`: `ws2_32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LoadWSAPoll(int (**a1)(struct pollfd *const, unsigned int, int), HINSTANCE *a2)
{
  HMODULE v4; // rax
  DWORD v5; // eax
  DWORD LastError; // ebx
  DWORD v7; // r15d
  int (*ProcAddress)(struct pollfd *const, unsigned int, int); // rax
  DWORD v9; // eax
  __int64 v11; // [rsp+78h] [rbp+10h] BYREF

  v11 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7CA0[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_1005D39F0)(
      bidID,
      0,
      0,
      &v11,
      off_1005E7CA0[0],
      0);
  v4 = SNILoadSystemLibA("ws2_32.dll");
  *a2 = v4;
  if ( v4 )
  {
    ProcAddress = (int (*)(struct pollfd *const, unsigned int, int))GetProcAddress(v4, "WSAPoll");
    *a1 = ProcAddress;
    if ( ProcAddress )
    {
      LastError = 0;
      goto LABEL_28;
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( (bidGblFlags & 2) != 0 && off_1005E5660[0] )
      bidTraceW(0, 326656, off_1005E5660[0], LastError);
    if ( (bidGblFlags & 2) != 0 && off_1005E5668[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 327680, off_1005E5668[0], 7);
    }
  }
  else
  {
    v5 = GetLastError();
    LastError = v5;
    if ( (bidGblFlags & 2) != 0 && off_1005E5650[0] )
      bidTraceW(0, 317440, off_1005E5650[0], v5);
    if ( (bidGblFlags & 2) != 0 && off_1005E5658[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 318464, off_1005E5658[0], 7);
    }
    v7 = LastError;
  }
  SNISetLastError(7, v7, 50100);
  if ( LastError && *a2 )
  {
    if ( !FreeLibrary(*a2) )
    {
      v9 = GetLastError();
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1005E5670[0] )
          bidTraceW(0, 339968, off_1005E5670[0], v9);
      }
    }
    *a2 = 0;
    *a1 = 0;
  }
LABEL_28:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5678[0] )
    bidTraceW(0, 345088, off_1005E5678[0], LastError);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v11);
  return LastError;
}

```

## disassembly

```asm
0x1004354b4  mov     r11, rsp
0x1004354b7  push    r12
0x1004354b9  push    r14
0x1004354bb  push    r15
0x1004354bd  sub     rsp, 50h
0x1004354c1  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x1004354c9  mov     [r11+8], rbx
0x1004354cd  mov     [r11+18h], rbp
0x1004354d1  mov     [r11+20h], rsi
0x1004354d5  mov     r14, rdx
0x1004354d8  mov     r12, rcx
0x1004354db  or      qword ptr [r11+10h], 0FFFFFFFFFFFFFFFFh
0x1004354e0  mov     eax, cs:_bidGblFlags
0x1004354e6  mov     ecx, 20004h
0x1004354eb  and     eax, ecx
0x1004354ed  cmp     eax, ecx
0x1004354ef  jnz     short loc_100435534
0x1004354f1  mov     rax, cs:off_1005E7CA0; "<LoadWSAPoll|API|SNI> "
0x1004354f8  test    rax, rax
0x1004354fb  jz      short loc_100435534
0x1004354fd  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100435505  jz      short loc_100435534
0x100435507  mov     rax, cs:off_1005D39F0
0x10043550e  and     qword ptr [r11-40h], 0
0x100435513  mov     rcx, cs:off_1005E7CA0; "<LoadWSAPoll|API|SNI> "
0x10043551a  mov     [r11-48h], rcx
0x10043551e  lea     r9, [r11+10h]
0x100435522  xor     r8d, r8d
0x100435525  xor     edx, edx
0x100435527  mov     rcx, cs:_bidID
0x10043552e  call    cs:__guard_dispatch_icall_fptr
0x100435534  lea     rcx, aWs232Dll_0; "ws2_32.dll"
0x10043553b  call    SNILoadSystemLibA
0x100435540  mov     [r14], rax
0x100435543  test    rax, rax
0x100435546  jnz     short loc_1004355C7
0x100435548  call    cs:__imp_GetLastError
0x10043554e  mov     ebx, eax
0x100435550  test    byte ptr cs:_bidGblFlags, 2
0x100435557  jz      short loc_10043557B
0x100435559  mov     rcx, cs:off_1005E5650; "<LoadWSAPoll|ERR|SNI> SNILoadSystemLibA"...
0x100435560  test    rcx, rcx
0x100435563  jz      short loc_10043557B
0x100435565  mov     r9d, eax
0x100435568  mov     r8, cs:off_1005E5650; "<LoadWSAPoll|ERR|SNI> SNILoadSystemLibA"...
0x10043556f  mov     edx, 4D800h
0x100435574  xor     ecx, ecx
0x100435576  call    _bidTraceW
0x10043557b  mov     ebp, 0C3B4h
0x100435580  mov     esi, 7
0x100435585  test    byte ptr cs:_bidGblFlags, 2
0x10043558c  jz      short loc_1004355BF
0x10043558e  mov     rax, cs:off_1005E5658; "<LoadWSAPoll|ERR|SNI> ProviderNum: %d{P"...
0x100435595  test    rax, rax
0x100435598  jz      short loc_1004355BF
0x10043559a  mov     ecx, ebp; unsigned int
0x10043559c  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1004355a1  mov     [rsp+68h+var_40], ebx
0x1004355a5  mov     [rsp+68h+var_48], eax
0x1004355a9  mov     r9d, esi
0x1004355ac  mov     r8, cs:off_1005E5658; "<LoadWSAPoll|ERR|SNI> ProviderNum: %d{P"...
0x1004355b3  mov     edx, 4DC00h
0x1004355b8  xor     ecx, ecx
0x1004355ba  call    _bidTraceW
0x1004355bf  mov     r15d, ebx
0x1004355c2  jmp     loc_10043565E
0x1004355c7  lea     rdx, aWsapoll; "WSAPoll"
0x1004355ce  mov     rcx, rax; hModule
0x1004355d1  call    cs:__imp_GetProcAddress
0x1004355d7  mov     [r12], rax
0x1004355db  test    rax, rax
0x1004355de  jnz     loc_1004356BD
0x1004355e4  call    cs:__imp_GetLastError
0x1004355ea  mov     ebx, eax
0x1004355ec  mov     r15d, eax
0x1004355ef  test    byte ptr cs:_bidGblFlags, 2
0x1004355f6  jz      short loc_10043561A
0x1004355f8  mov     rax, cs:off_1005E5660; "<LoadWSAPoll|ERR|SNI> GetProcAddress fo"...
0x1004355ff  test    rax, rax
0x100435602  jz      short loc_10043561A
0x100435604  mov     r9d, ebx
0x100435607  mov     r8, cs:off_1005E5660; "<LoadWSAPoll|ERR|SNI> GetProcAddress fo"...
0x10043560e  mov     edx, 4FC00h
0x100435613  xor     ecx, ecx
0x100435615  call    _bidTraceW
0x10043561a  mov     ebp, 0C3B4h
0x10043561f  mov     esi, 7
0x100435624  test    byte ptr cs:_bidGblFlags, 2
0x10043562b  jz      short loc_10043565E
0x10043562d  mov     rax, cs:off_1005E5668; "<LoadWSAPoll|ERR|SNI> ProviderNum: %d{P"...
0x100435634  test    rax, rax
0x100435637  jz      short loc_10043565E
0x100435639  mov     ecx, ebp; unsigned int
0x10043563b  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100435640  mov     [rsp+68h+var_40], ebx
0x100435644  mov     [rsp+68h+var_48], eax
0x100435648  mov     r9d, esi
0x10043564b  mov     r8, cs:off_1005E5668; "<LoadWSAPoll|ERR|SNI> ProviderNum: %d{P"...
0x100435652  mov     edx, 50000h
0x100435657  xor     ecx, ecx
0x100435659  call    _bidTraceW
0x10043565e  mov     r8d, ebp
0x100435661  mov     edx, r15d
0x100435664  mov     ecx, esi
0x100435666  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043566b  test    ebx, ebx
0x10043566d  jz      short loc_1004356BF
0x10043566f  mov     rcx, [r14]; hLibModule
0x100435672  test    rcx, rcx
0x100435675  jz      short loc_1004356BF
0x100435677  call    cs:__imp_FreeLibrary
0x10043567d  test    eax, eax
0x10043567f  jnz     short loc_1004356B2
0x100435681  call    cs:__imp_GetLastError
0x100435687  test    byte ptr cs:_bidGblFlags, 2
0x10043568e  jz      short loc_1004356B2
0x100435690  mov     rcx, cs:off_1005E5670; "<LoadWSAPoll|ERR|SNI> FreeLibrary for w"...
0x100435697  test    rcx, rcx
0x10043569a  jz      short loc_1004356B2
0x10043569c  mov     r9d, eax
0x10043569f  mov     r8, cs:off_1005E5670; "<LoadWSAPoll|ERR|SNI> FreeLibrary for w"...
0x1004356a6  mov     edx, 53000h
0x1004356ab  xor     ecx, ecx
0x1004356ad  call    _bidTraceW
0x1004356b2  and     qword ptr [r14], 0
0x1004356b6  and     qword ptr [r12], 0
0x1004356bb  jmp     short loc_1004356BF
0x1004356bd  xor     ebx, ebx
0x1004356bf  mov     eax, cs:_bidGblFlags
0x1004356c5  mov     ecx, 20002h
0x1004356ca  and     eax, ecx
0x1004356cc  cmp     eax, ecx
0x1004356ce  jnz     short loc_1004356F3
0x1004356d0  mov     rax, cs:off_1005E5678; "<LoadWSAPoll|RET|SNI> %d{WINERR}\n"
0x1004356d7  test    rax, rax
0x1004356da  jz      short loc_1004356F3
0x1004356dc  mov     r9d, ebx
0x1004356df  mov     r8, cs:off_1005E5678; "<LoadWSAPoll|RET|SNI> %d{WINERR}\n"
0x1004356e6  mov     edx, 54400h
0x1004356eb  xor     ecx, ecx
0x1004356ed  call    _bidTraceW
0x1004356f2  nop
0x1004356f3  lea     rcx, [rsp+68h+arg_8]; this
0x1004356f8  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1004356fd  mov     eax, ebx
0x1004356ff  lea     r11, [rsp+68h+var_18]
0x100435704  mov     rbx, [r11+20h]
0x100435708  mov     rbp, [r11+30h]
0x10043570c  mov     rsi, [r11+38h]
0x100435710  mov     rsp, r11
0x100435713  pop     r15
0x100435715  pop     r14
0x100435717  pop     r12
0x100435719  retn
```
