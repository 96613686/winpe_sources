# CDirectMusic::Init(void)

- ea: `0x1800138f0`
- end: `0x180013a80`
- name: `?Init@CDirectMusic@@QEAAJXZ`
- size: `400`
- prototype: `__int64 __fastcall(CDirectMusic *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d1e0`

## callees

- `0x18000ae14`
- `0x1800138f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013904`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013904`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180013a07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180013a4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180013a07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180013a4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800139c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800139c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013a68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013a68`

## pseudocode

```c
__int64 __fastcall CDirectMusic::Init(CDirectMusic *this)
{
  volatile signed __int32 *v2; // rax
  __int64 result; // rax
  int v4; // edi
  volatile signed __int32 *Data; // [rsp+60h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+30h] BYREF
  DWORD Type; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  v2 = (volatile signed __int32 *)malloc(0x88u);
  Data = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &CMasterClock::`vftable'{for `IReferenceClock'};
    *((_QWORD *)v2 + 1) = &CMasterClock::`vftable'{for `IDirectSoundSinkSync'};
    *((_QWORD *)v2 + 2) = &CMasterClock::`vftable'{for `IMasterClockPrivate'};
    *((_QWORD *)v2 + 4) = &CList<IDirectMusicPort *>::`vftable';
    *((_QWORD *)v2 + 5) = 0;
    *((_QWORD *)v2 + 6) = 0;
    *((_DWORD *)v2 + 14) = 0;
    *((_QWORD *)v2 + 3) = 0;
    *((_QWORD *)v2 + 10) = 0;
    *((_QWORD *)v2 + 12) = 0;
    *((_QWORD *)v2 + 14) = 0;
    *((_QWORD *)v2 + 13) = 0;
    *((_QWORD *)v2 + 15) = 0;
    *((_QWORD *)v2 + 16) = 0;
    *((_QWORD *)v2 + 11) = 0;
  }
  else
  {
    v2 = 0;
  }
  *((_QWORD *)this + 12) = v2;
  if ( !v2 )
    return 2147942414LL;
  _InterlockedIncrement(v2 + 7);
  result = CMasterClock::Init(*((CMasterClock **)this + 12));
  v4 = result;
  if ( (int)result >= 0 )
  {
    *((_QWORD *)this + 17) = 0;
    hKey = 0;
    if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\DirectMusic", 0, 0x20019u, &hKey) )
    {
      Type = 0;
      LODWORD(Data) = 0;
      cbData = 4;
      if ( !RegQueryValueExA(hKey, "DefaultToMsKernelSynth", 0, &Type, (LPBYTE)&Data, &cbData) && (_DWORD)Data )
        *((_DWORD *)this + 34) = 1;
      cbData = 4;
      if ( !RegQueryValueExA(hKey, "DisableHWAcceleration", 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        if ( (_DWORD)Data )
          *((_DWORD *)this + 35) = 1;
      }
      RegCloseKey(hKey);
    }
    return v4 != 0 ? 0x80004002 : 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800138f0  push    rbp
0x1800138f2  push    rbx
0x1800138f3  push    rsi
0x1800138f4  push    rdi
0x1800138f5  mov     rbp, rsp
0x1800138f8  sub     rsp, 38h
0x1800138fc  mov     rbx, rcx
0x1800138ff  mov     ecx, 88h; Size
0x180013904  call    cs:__imp_malloc
0x18001390a  xor     esi, esi
0x18001390c  mov     [rbp+Data], rax
0x180013910  test    rax, rax
0x180013913  jz      short loc_180013970
0x180013915  lea     rcx, ??_7CMasterClock@@6BIReferenceClock@@@; const CMasterClock::`vftable'{for `IReferenceClock'}
0x18001391c  mov     [rax], rcx
0x18001391f  lea     rcx, ??_7CMasterClock@@6BIDirectSoundSinkSync@@@; const CMasterClock::`vftable'{for `IDirectSoundSinkSync'}
0x180013926  mov     [rax+8], rcx
0x18001392a  lea     rcx, ??_7CMasterClock@@6BIMasterClockPrivate@@@; const CMasterClock::`vftable'{for `IMasterClockPrivate'}
0x180013931  mov     [rax+10h], rcx
0x180013935  lea     rcx, ??_7?$CList@PEAUIDirectMusicPort@@@@6B@; const CList<IDirectMusicPort *>::`vftable'
0x18001393c  mov     [rax+20h], rcx
0x180013940  mov     [rax+28h], rsi
0x180013944  mov     [rax+30h], rsi
0x180013948  mov     [rax+38h], esi
0x18001394b  mov     [rax+18h], rsi
0x18001394f  mov     [rax+50h], rsi
0x180013953  mov     [rax+60h], rsi
0x180013957  mov     [rax+70h], rsi
0x18001395b  mov     [rax+68h], rsi
0x18001395f  mov     [rax+78h], rsi
0x180013963  mov     [rax+80h], rsi
0x18001396a  mov     [rax+58h], rsi
0x18001396e  jmp     short loc_180013973
0x180013970  mov     rax, rsi
0x180013973  mov     [rbx+60h], rax
0x180013977  test    rax, rax
0x18001397a  jnz     short loc_180013986
0x18001397c  mov     eax, 8007000Eh
0x180013981  jmp     loc_180013A77
0x180013986  lock inc dword ptr [rax+1Ch]
0x18001398a  mov     rcx, [rbx+60h]; this
0x18001398e  call    ?Init@CMasterClock@@QEAAJXZ; CMasterClock::Init(void)
0x180013993  mov     edi, eax
0x180013995  test    eax, eax
0x180013997  js      loc_180013A77
0x18001399d  lea     rax, [rbp+hKey]
0x1800139a1  mov     [rbx+88h], rsi
0x1800139a8  mov     r9d, 20019h; samDesired
0x1800139ae  mov     [rsp+38h+phkResult], rax; phkResult
0x1800139b3  xor     r8d, r8d; ulOptions
0x1800139b6  mov     [rbp+hKey], rsi
0x1800139ba  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\DirectMusic"
0x1800139c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800139c8  call    cs:__imp_RegOpenKeyExA
0x1800139ce  test    eax, eax
0x1800139d0  jnz     loc_180013A6E
0x1800139d6  mov     rcx, [rbp+hKey]; hKey
0x1800139da  lea     rax, [rbp+cbData]
0x1800139de  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800139e3  lea     r9, [rbp+Type]; lpType
0x1800139e7  lea     rax, [rbp+Data]
0x1800139eb  mov     [rbp+Type], esi
0x1800139ee  xor     r8d, r8d; lpReserved
0x1800139f1  mov     [rsp+38h+phkResult], rax; lpData
0x1800139f6  lea     rdx, aDefaulttomsker; "DefaultToMsKernelSynth"
0x1800139fd  mov     dword ptr [rbp+Data], esi
0x180013a00  mov     [rbp+cbData], 4
0x180013a07  call    cs:__imp_RegQueryValueExA
0x180013a0d  test    eax, eax
0x180013a0f  jnz     short loc_180013A20
0x180013a11  cmp     dword ptr [rbp+Data], esi
0x180013a14  jz      short loc_180013A20
0x180013a16  mov     dword ptr [rbx+88h], 1
0x180013a20  mov     rcx, [rbp+hKey]; hKey
0x180013a24  lea     rax, [rbp+cbData]
0x180013a28  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180013a2d  lea     r9, [rbp+Type]; lpType
0x180013a31  lea     rax, [rbp+Data]
0x180013a35  mov     [rbp+cbData], 4
0x180013a3c  xor     r8d, r8d; lpReserved
0x180013a3f  mov     [rsp+38h+phkResult], rax; lpData
0x180013a44  lea     rdx, aDisablehwaccel; "DisableHWAcceleration"
0x180013a4b  call    cs:__imp_RegQueryValueExA
0x180013a51  test    eax, eax
0x180013a53  jnz     short loc_180013A64
0x180013a55  cmp     dword ptr [rbp+Data], esi
0x180013a58  jz      short loc_180013A64
0x180013a5a  mov     dword ptr [rbx+8Ch], 1
0x180013a64  mov     rcx, [rbp+hKey]; hKey
0x180013a68  call    cs:__imp_RegCloseKey
0x180013a6e  neg     edi
0x180013a70  sbb     eax, eax
0x180013a72  and     eax, 80004002h
0x180013a77  add     rsp, 38h
0x180013a7b  pop     rdi
0x180013a7c  pop     rsi
0x180013a7d  pop     rbx
0x180013a7e  pop     rbp
0x180013a7f  retn
```
