# PortMgrDeleteAll

- ea: `0x180023770`
- end: `0x1800238b2`
- name: `PortMgrDeleteAll`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ee7c`

## callees

- `0x180005440`
- `0x18001e824`
- `0x1800214f0`
- `0x180023770`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023864`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023864`
- `MobileNetworking!ReleaseWriteLock` at `0x180023850`
- `MobileNetworking!ReleaseWriteLock` at `0x180023850`
- `MobileNetworking!AcquireWriteLock` at `0x1800237cb`
- `MobileNetworking!AcquireWriteLock` at `0x1800237cb`

## string_xrefs

- `0x1800237b6`: `PortMgrDeleteAll`
- `0x18002383b`: `PortMgrDeleteAll`

## pseudocode

```c
__int64 PortMgrDeleteAll()
{
  _QWORD *i; // rax
  __int64 v1; // rcx
  _QWORD *v2; // rdx
  _QWORD *v3; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 49, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
  AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDeleteAll", 486);
  for ( i = (_QWORD *)qword_18003DD68; (__int64 *)qword_18003DD68 != &qword_18003DD68; i = (_QWORD *)qword_18003DD68 )
  {
    v1 = *i;
    if ( *(_QWORD **)(*i + 8LL) != i
      || (v2 = (_QWORD *)i[1], (_QWORD *)*v2 != i)
      || (*v2 = v1,
          *(_QWORD *)(v1 + 8) = v2,
          v3 = (_QWORD *)qword_18003DD80,
          *(__int64 **)qword_18003DD80 != &qword_18003DD78) )
    {
      __fastfail(3u);
    }
    i[1] = qword_18003DD80;
    *i = &qword_18003DD78;
    *v3 = i;
    qword_18003DD80 = (__int64)i;
    PortMgrDeletePortHelper((__int64)i);
  }
  ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDeleteAll", 511);
  while ( HIDWORD(qword_18003DD8C) )
    Sleep(0x64u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 50, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180023770  mov     [rsp+arg_0], rbp
0x180023775  mov     [rsp+arg_8], rsi
0x18002377a  push    rdi
0x18002377b  sub     rsp, 20h
0x18002377f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023786  lea     rdi, WPP_GLOBAL_Control
0x18002378d  cmp     rcx, rdi
0x180023790  jz      short loc_1800237B0
0x180023792  test    dword ptr [rcx+44h], 800h
0x180023799  jz      short loc_1800237B0
0x18002379b  mov     rcx, [rcx+38h]
0x18002379f  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x1800237a6  mov     edx, 31h ; '1'
0x1800237ab  call    WPP_SF_
0x1800237b0  mov     r9d, 1E6h
0x1800237b6  lea     r8, aPortmgrdeletea; "PortMgrDeleteAll"
0x1800237bd  lea     rdx, qword_18003DD98
0x1800237c4  lea     rcx, g_OneXInfo
0x1800237cb  call    cs:__imp_AcquireWriteLock
0x1800237d1  mov     rax, cs:qword_18003DD68
0x1800237d8  lea     rbp, qword_18003DD68
0x1800237df  cmp     rax, rbp
0x1800237e2  jz      short loc_180023835
0x1800237e4  lea     rsi, qword_18003DD78
0x1800237eb  mov     rcx, [rax]
0x1800237ee  cmp     [rcx+8], rax
0x1800237f2  jnz     short loc_180023858
0x1800237f4  mov     rdx, [rax+8]
0x1800237f8  cmp     [rdx], rax
0x1800237fb  jnz     short loc_180023858
0x1800237fd  mov     [rdx], rcx
0x180023800  mov     [rcx+8], rdx
0x180023804  mov     rcx, cs:qword_18003DD80
0x18002380b  cmp     [rcx], rsi
0x18002380e  jnz     short loc_180023858
0x180023810  mov     [rax+8], rcx
0x180023814  mov     [rax], rsi
0x180023817  mov     [rcx], rax
0x18002381a  mov     rcx, rax
0x18002381d  mov     cs:qword_18003DD80, rax
0x180023824  call    PortMgrDeletePortHelper
0x180023829  mov     rax, cs:qword_18003DD68
0x180023830  cmp     rax, rbp
0x180023833  jnz     short loc_1800237EB
0x180023835  mov     r9d, 1FFh
0x18002383b  lea     r8, aPortmgrdeletea; "PortMgrDeleteAll"
0x180023842  lea     rdx, qword_18003DD98
0x180023849  lea     rcx, g_OneXInfo
0x180023850  call    cs:__imp_ReleaseWriteLock
0x180023856  jmp     short loc_18002386A
0x180023858  mov     ecx, 3
0x18002385d  int     29h; Win8: RtlFailFast(ecx)
0x18002385f  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180023864  call    cs:__imp_Sleep
0x18002386a  cmp     dword ptr cs:qword_18003DD8C+4, 0
0x180023871  jnz     short loc_18002385F
0x180023873  mov     rcx, cs:WPP_GLOBAL_Control
0x18002387a  cmp     rcx, rdi
0x18002387d  jz      short loc_1800238A0
0x18002387f  test    dword ptr [rcx+44h], 800h
0x180023886  jz      short loc_1800238A0
0x180023888  mov     rcx, [rcx+38h]
0x18002388c  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180023893  mov     edx, 32h ; '2'
0x180023898  xor     r9d, r9d
0x18002389b  call    WPP_SF_D
0x1800238a0  mov     rbp, [rsp+28h+arg_0]
0x1800238a5  xor     eax, eax
0x1800238a7  mov     rsi, [rsp+28h+arg_8]
0x1800238ac  add     rsp, 20h
0x1800238b0  pop     rdi
0x1800238b1  retn
```
