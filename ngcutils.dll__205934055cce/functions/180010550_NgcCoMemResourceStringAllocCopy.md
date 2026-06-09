# NgcCoMemResourceStringAllocCopy

- ea: `0x180010550`
- end: `0x1800105ed`
- name: `NgcCoMemResourceStringAllocCopy`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a5b4`
- `0x180010550`
- `0x1800128a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800105c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800105c7`

## string_xrefs

- `0x18001056f`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x1800105ac`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`

## pseudocode

```c
__int64 __fastcall NgcCoMemResourceStringAllocCopy(NgcUtils *a1, HINSTANCE a2, LPVOID *a3, unsigned __int16 **a4)
{
  int v6; // eax
  unsigned int v7; // edi
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPVOID pv; // [rsp+40h] [rbp+18h] BYREF

  if ( a3 )
  {
    *a3 = 0;
    pv = 0;
    v6 = NgcUtils::CoMemResourceStringAllocCopy(a1, a2, (unsigned int)&pv, a4);
    v7 = v6;
    if ( v6 >= 0 )
    {
      *a3 = pv;
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
        (const char *)(unsigned int)v6,
        v8);
      if ( pv )
        CoTaskMemFree(pv);
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v8);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180010550  mov     [rsp+arg_0], rbx
0x180010555  push    rdi; int
0x180010556  sub     rsp, 20h
0x18001055a  mov     rbx, r8
0x18001055d  test    rbx, rbx
0x180010560  jnz     short loc_180010584
0x180010562  mov     rcx, [rsp+28h]; this
0x180010567  mov     ebx, 80004003h
0x18001056c  mov     r9d, ebx; char *
0x18001056f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010576  mov     edx, 29h ; ')'; void *
0x18001057b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010580  mov     eax, ebx
0x180010582  jmp     short loc_1800105E1
0x180010584  mov     qword ptr [r8], 0
0x18001058b  mov     [rsp+28h+pv], 0
0x180010594  lea     r8, [rsp+28h+pv]; unsigned int
0x180010599  call    ?CoMemResourceStringAllocCopy@NgcUtils@@YAJPEAUHINSTANCE__@@IPEAPEAG@Z; NgcUtils::CoMemResourceStringAllocCopy(HINSTANCE__ *,uint,ushort * *)
0x18001059e  mov     edi, eax
0x1800105a0  test    eax, eax
0x1800105a2  jns     short loc_1800105D1
0x1800105a4  mov     rcx, [rsp+28h]; this
0x1800105a9  mov     r9d, eax; char *
0x1800105ac  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800105b3  mov     edx, 2Dh ; '-'; void *
0x1800105b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800105bd  mov     rcx, [rsp+28h+pv]; pv
0x1800105c2  test    rcx, rcx
0x1800105c5  jz      short loc_1800105CD
0x1800105c7  call    cs:__imp_CoTaskMemFree
0x1800105cd  mov     eax, edi
0x1800105cf  jmp     short loc_1800105E1
0x1800105d1  mov     rax, [rsp+28h+pv]
0x1800105d6  mov     [rbx], rax
0x1800105d9  xor     eax, eax
0x1800105db  jmp     short loc_1800105E1
0x1800105dd  mov     eax, dword ptr [rsp+28h+pv]
0x1800105e1  mov     rbx, [rsp+28h+arg_0]
0x1800105e6  add     rsp, 20h
0x1800105ea  pop     rdi
0x1800105eb  retn
```
