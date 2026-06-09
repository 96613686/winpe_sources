# CWMDeColorConvDMO::RegisterThreads(ulong,ushort const *)

- ea: `0x18000dfb0`
- end: `0x18000e055`
- name: `?RegisterThreads@CWMDeColorConvDMO@@UEAAJKPEBG@Z`
- size: `165`
- prototype: `int(CWMDeColorConvDMO *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000dfb0`
- `0x18000e440`
- `0x1800149ec`
- `0x180014a18`

## pseudocode

```c
__int64 __fastcall CWMDeColorConvDMO::RegisterThreads(
        CWMDeColorConvDMO *this,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rdi
  __int64 result; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r11
  void *v8; // rcx
  __int64 v9; // r11
  void *v10; // rcx
  __int64 v11; // r11

  v3 = (unsigned __int16 *)((char *)this + 220);
  result = StringCchCopyW((unsigned __int16 *)this + 110, 0x100u, a3);
  if ( (int)result >= 0 )
  {
    if ( !a2 )
      return 2147500037LL;
    v8 = *(void **)(v7 + 32);
    *(_DWORD *)(v7 + 736) = a2;
    *(_DWORD *)(v7 + 732) = 1;
    if ( v8 )
    {
      if ( (unsigned int)setColorConvThreadClass(v8, v6, v3, a2)
        || (unsigned int)setMMCSSRegisterCC(*(void **)(v9 + 32), 1) )
      {
        return 2147500037LL;
      }
    }
    v10 = *(void **)(v7 + 48);
    if ( v10
      && ((unsigned int)setColorConvThreadClass(v10, v6, v3, *(_DWORD *)(v7 + 736))
       || (unsigned int)setMMCSSRegisterCC(*(void **)(v11 + 48), 1)) )
    {
      return 2147500037LL;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000dfb0  mov     [rsp+arg_0], rbx
0x18000dfb5  push    rdi
0x18000dfb6  sub     rsp, 20h
0x18000dfba  lea     rdi, [rcx+0DCh]
0x18000dfc1  mov     ebx, edx
0x18000dfc3  mov     r11, rcx
0x18000dfc6  mov     edx, 100h; unsigned __int64
0x18000dfcb  mov     rcx, rdi; unsigned __int16 *
0x18000dfce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dfd3  test    eax, eax
0x18000dfd5  js      short loc_18000E04A
0x18000dfd7  test    ebx, ebx
0x18000dfd9  jz      short loc_18000E045
0x18000dfdb  mov     rcx, [r11+20h]; void *
0x18000dfdf  mov     [r11+2E0h], ebx
0x18000dfe6  mov     dword ptr [r11+2DCh], 1
0x18000dff1  test    rcx, rcx
0x18000dff4  jz      short loc_18000E015
0x18000dff6  mov     r9d, ebx; unsigned int
0x18000dff9  mov     r8, rdi; unsigned __int16 *
0x18000dffc  call    ?setColorConvThreadClass@@YAJPEAX_KPEAGK@Z; setColorConvThreadClass(void *,unsigned __int64,ushort *,ulong)
0x18000e001  test    eax, eax
0x18000e003  jnz     short loc_18000E045
0x18000e005  mov     rcx, [r11+20h]; void *
0x18000e009  lea     edx, [rax+1]; int
0x18000e00c  call    ?setMMCSSRegisterCC@@YAJPEAXH@Z; setMMCSSRegisterCC(void *,int)
0x18000e011  test    eax, eax
0x18000e013  jnz     short loc_18000E045
0x18000e015  mov     rcx, [r11+30h]; void *
0x18000e019  test    rcx, rcx
0x18000e01c  jz      short loc_18000E041
0x18000e01e  mov     r9d, [r11+2E0h]; unsigned int
0x18000e025  mov     r8, rdi; unsigned __int16 *
0x18000e028  call    ?setColorConvThreadClass@@YAJPEAX_KPEAGK@Z; setColorConvThreadClass(void *,unsigned __int64,ushort *,ulong)
0x18000e02d  test    eax, eax
0x18000e02f  jnz     short loc_18000E045
0x18000e031  mov     rcx, [r11+30h]; void *
0x18000e035  lea     edx, [rax+1]; int
0x18000e038  call    ?setMMCSSRegisterCC@@YAJPEAXH@Z; setMMCSSRegisterCC(void *,int)
0x18000e03d  test    eax, eax
0x18000e03f  jnz     short loc_18000E045
0x18000e041  xor     eax, eax
0x18000e043  jmp     short loc_18000E04A
0x18000e045  mov     eax, 80004005h
0x18000e04a  mov     rbx, [rsp+28h+arg_0]
0x18000e04f  add     rsp, 20h
0x18000e053  pop     rdi
0x18000e054  retn
```
