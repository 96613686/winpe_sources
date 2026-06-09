# NgcUtils::GetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x18001cb68`
- end: `0x18001cbfb`
- name: `?GetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `147`
- prototype: `__int64 __fastcall(NgcUtils *this, HKEY, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013220`
- `0x180014c24`

## callees

- `0x18000cc34`
- `0x18001cb68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cba9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cba9`

## string_xrefs

- `0x18001cbd0`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetRegistryDwordValue(
        NgcUtils *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  LSTATUS ValueW; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-38h]
  DWORD v9[6]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v11; // [rsp+68h] [rbp+10h] BYREF
  int v12; // [rsp+6Ch] [rbp+14h]

  v12 = HIDWORD(a2);
  v9[0] = 4;
  v11 = 0;
  ValueW = RegGetValueW((HKEY)this, 0, a3, 0x10u, 0, &v11, v9);
  v6 = ValueW;
  if ( ValueW > 0 )
    v6 = (unsigned __int16)ValueW | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
  {
    *(_DWORD *)a4 = v11;
    return 0;
  }
  else
  {
    result = 2147942402LL;
    if ( v6 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
        (const char *)v6,
        v8);
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001cb68  mov     r11, rsp
0x18001cb6b  mov     [r11+8], rbx
0x18001cb6f  mov     [r11+10h], rdx
0x18001cb73  push    rdi
0x18001cb74  sub     rsp, 50h
0x18001cb78  lea     rax, [r11-18h]
0x18001cb7c  mov     [rsp+58h+var_18], 4
0x18001cb84  mov     [r11-28h], rax
0x18001cb88  xor     edx, edx; lpSubKey
0x18001cb8a  lea     rax, [r11+10h]
0x18001cb8e  mov     [rsp+58h+arg_8], 0
0x18001cb96  mov     rdi, r9
0x18001cb99  mov     [r11-30h], rax
0x18001cb9d  mov     qword ptr [r11-38h], 0
0x18001cba5  lea     r9d, [rdx+10h]; dwFlags
0x18001cba9  call    cs:__imp_RegGetValueW
0x18001cbaf  mov     ebx, eax
0x18001cbb1  test    eax, eax
0x18001cbb3  jle     short loc_18001CBBE
0x18001cbb5  movzx   ebx, ax
0x18001cbb8  or      ebx, 80070000h
0x18001cbbe  test    ebx, ebx
0x18001cbc0  jns     short loc_18001CBE8
0x18001cbc2  mov     eax, 80070002h
0x18001cbc7  cmp     ebx, eax
0x18001cbc9  jz      short loc_18001CBF0
0x18001cbcb  mov     rcx, [rsp+58h]; this
0x18001cbd0  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001cbd7  mov     r9d, ebx; char *
0x18001cbda  mov     edx, 4Eh ; 'N'; void *
0x18001cbdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cbe4  mov     eax, ebx
0x18001cbe6  jmp     short loc_18001CBF0
0x18001cbe8  mov     eax, [rsp+58h+arg_8]
0x18001cbec  mov     [rdi], eax
0x18001cbee  xor     eax, eax
0x18001cbf0  mov     rbx, [rsp+58h+arg_0]
0x18001cbf5  add     rsp, 50h
0x18001cbf9  pop     rdi
0x18001cbfa  retn
```
