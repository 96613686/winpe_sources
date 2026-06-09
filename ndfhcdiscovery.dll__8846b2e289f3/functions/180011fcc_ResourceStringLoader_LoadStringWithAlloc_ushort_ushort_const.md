# ResourceStringLoader::LoadStringWithAlloc(ushort * *,ushort const *)

- ea: `0x180011fcc`
- end: `0x18001213e`
- name: `?LoadStringWithAlloc@ResourceStringLoader@@QEAAJPEAPEAGPEBG@Z`
- size: `370`
- prototype: `int(ResourceStringLoader *__hidden this, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x18000b6fc`
- `0x18000cfe4`
- `0x18000d990`
- `0x18000dac0`
- `0x18000dd80`

## callees

- `0x18001032c`
- `0x180010684`
- `0x180011f1c`
- `0x180011fcc`
- `0x180012144`
- `0x180013686`
- `0x1800136b0`
- `0x180015010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800120f0`
- `KERNEL32!FreeLibrary` at `0x1800120f0`
- `KERNEL32!GetLastError` at `0x180012100`
- `KERNEL32!GetLastError` at `0x180012100`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall ResourceStringLoader::LoadStringWithAlloc(
        ResourceStringLoader *this,
        unsigned __int16 **a2,
        const unsigned __int16 *a3)
{
  int result; // eax
  unsigned int v6; // edx
  ResourceStringLoader *v7; // rcx
  unsigned __int16 *HandleToModule; // rax
  HMODULE v9; // rdi
  const unsigned __int16 *v10; // r8
  unsigned __int16 *v11; // rbx
  int v12; // esi
  unsigned __int16 *v13; // rdx
  int v14; // [rsp+30h] [rbp-248h] BYREF
  unsigned __int16 *v15[3]; // [rsp+38h] [rbp-240h] BYREF
  unsigned __int16 v16[264]; // [rsp+50h] [rbp-228h] BYREF

  if ( !a3 )
    return -2147024894;
  memset_0(v16, 0, 0x208u);
  v14 = 0;
  result = ParseResourceString(v16, v6, &v14, a3);
  if ( result >= 0 )
  {
    HandleToModule = (unsigned __int16 *)ResourceStringLoader::GetHandleToModule(v7, v16);
    v9 = (HMODULE)HandleToModule;
    if ( HandleToModule )
    {
      v15[1] = HandleToModule;
      v15[0] = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                           v15,
                           v9,
                           (unsigned int)v14) )
      {
        v11 = v15[0];
        v12 = UtilAssembleStringsWithAlloc(a2, 0xFFFFu, v10, v15[0]);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
      }
      else
      {
        v13 = v15[0] - 12;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15[0] - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
        v12 = -2147024894;
      }
      FreeLibrary(v9);
      return v12;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011fcc  mov     [rsp+arg_0], rbx
0x180011fd1  mov     [rsp+arg_18], rsi
0x180011fd6  push    rdi
0x180011fd7  sub     rsp, 270h
0x180011fde  mov     rax, cs:__security_cookie
0x180011fe5  xor     rax, rsp
0x180011fe8  mov     [rsp+278h+var_18], rax
0x180011ff0  mov     rbx, r8
0x180011ff3  mov     rsi, rdx
0x180011ff6  test    r8, r8
0x180011ff9  jnz     short loc_180012005
0x180011ffb  mov     eax, 80070002h
0x180012000  jmp     loc_180012118
0x180012005  xor     edx, edx; Val
0x180012007  mov     r8d, 208h; Size
0x18001200d  lea     rcx, [rsp+278h+var_228]; void *
0x180012012  call    memset_0
0x180012017  mov     [rsp+278h+var_248], 0
0x18001201f  mov     r9, rbx; unsigned __int16 *
0x180012022  lea     r8, [rsp+278h+var_248]; int *
0x180012027  lea     rcx, [rsp+278h+var_228]; unsigned __int16 *
0x18001202c  call    ?ParseResourceString@@YAJPEAGKPEAHPEBG@Z; ParseResourceString(ushort *,ulong,int *,ushort const *)
0x180012031  test    eax, eax
0x180012033  js      loc_180012118
0x180012039  lea     rdx, [rsp+278h+var_228]; unsigned __int16 *
0x18001203e  call    ?GetHandleToModule@ResourceStringLoader@@AEAAPEAUHINSTANCE__@@PEBG@Z; ResourceStringLoader::GetHandleToModule(ushort const *)
0x180012043  mov     rdi, rax
0x180012046  test    rax, rax
0x180012049  jz      loc_180012100
0x18001204f  mov     [rsp+278h+var_238], rax
0x180012054  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001205b  mov     rax, [rcx+18h]
0x18001205f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180012066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001206b  add     rax, 18h
0x18001206f  mov     [rsp+278h+var_240], rax
0x180012074  mov     r8d, [rsp+278h+var_248]
0x180012079  mov     rdx, rdi
0x18001207c  lea     rcx, [rsp+278h+var_240]
0x180012081  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x180012086  test    eax, eax
0x180012088  jz      short loc_1800120C3
0x18001208a  mov     rbx, [rsp+278h+var_240]
0x18001208f  mov     r9, rbx; unsigned __int16 *
0x180012092  mov     edx, 0FFFFh; unsigned int
0x180012097  mov     rcx, rsi; unsigned __int16 **
0x18001209a  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x18001209f  mov     esi, eax
0x1800120a1  lea     rdx, [rbx-18h]
0x1800120a5  or      ecx, 0FFFFFFFFh
0x1800120a8  lock xadd [rdx+10h], ecx
0x1800120ad  sub     ecx, 1
0x1800120b0  jg      short loc_1800120ED
0x1800120b2  mov     rcx, [rdx]
0x1800120b5  mov     r8, [rcx]
0x1800120b8  mov     rax, [r8+8]
0x1800120bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120c1  jmp     short loc_1800120ED
0x1800120c3  mov     rdx, [rsp+278h+var_240]
0x1800120c8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800120cc  or      eax, 0FFFFFFFFh
0x1800120cf  lock xadd [rdx+10h], eax
0x1800120d4  sub     eax, 1
0x1800120d7  jg      short loc_1800120E8
0x1800120d9  mov     rcx, [rdx]
0x1800120dc  mov     rax, [rcx]
0x1800120df  mov     rax, [rax+8]
0x1800120e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120e8  mov     esi, 80070002h
0x1800120ed  mov     rcx, rdi; hLibModule
0x1800120f0  call    cs:__imp_FreeLibrary
0x1800120f7  nop     dword ptr [rax+rax+00h]
0x1800120fc  mov     eax, esi
0x1800120fe  jmp     short loc_180012118
0x180012100  call    cs:__imp_GetLastError
0x180012107  nop     dword ptr [rax+rax+00h]
0x18001210c  test    eax, eax
0x18001210e  jle     short loc_180012118
0x180012110  movzx   eax, ax
0x180012113  or      eax, 80070000h
0x180012118  mov     rcx, [rsp+278h+var_18]
0x180012120  xor     rcx, rsp; StackCookie
0x180012123  call    __security_check_cookie
0x180012128  lea     r11, [rsp+278h+var_8]
0x180012130  mov     rbx, [r11+10h]
0x180012134  mov     rsi, [r11+28h]
0x180012138  mov     rsp, r11
0x18001213b  pop     rdi
0x18001213c  retn
```
