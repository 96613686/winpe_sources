# MULTI_IPM::CreateServer(ushort const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x18002b4d0`
- end: `0x18002b562`
- name: `?CreateServer@MULTI_IPM@@QEAAJPEBGKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(MULTI_IPM *__hidden this, const unsigned __int16 *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800026d0`
- `0x180008000`
- `0x18002b4d0`
- `0x18002b570`

## string_xrefs

- `0x18002b535`: `MULTI_IPM::CreateServer failed InstantiatePipe hr=0x%08x \n `
- `0x18002b526`: `MULTI_IPM::CreateServer`
- `0x18002b53c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\multi_ipm.cxx`

## pseudocode

```c
__int64 __fastcall MULTI_IPM::CreateServer(
        MULTI_IPM *this,
        const unsigned __int16 *a2,
        int a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  int v7; // ebx
  int v8; // eax

  if ( !a2 || !*a2 || !a3 )
    return 2147942487LL;
  v7 = STRU::Copy(this, a2);
  if ( v7 >= 0 )
  {
    *((_DWORD *)this + 15) = a3;
    v8 = MULTI_IPM::InstantiatePipe(this, a4);
    v7 = v8;
    if ( v8 < 0 && (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\multi_ipm.cxx",
        0x3Eu,
        "MULTI_IPM::CreateServer",
        "MULTI_IPM::CreateServer failed InstantiatePipe hr=0x%08x \n ",
        v8);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002b4d0  push    rbx
0x18002b4d2  push    rbp
0x18002b4d3  push    rsi
0x18002b4d4  push    rdi
0x18002b4d5  push    r14
0x18002b4d7  sub     rsp, 30h
0x18002b4db  xor     r14d, r14d
0x18002b4de  mov     rbp, r9
0x18002b4e1  mov     esi, r8d
0x18002b4e4  mov     rdi, rcx
0x18002b4e7  test    rdx, rdx
0x18002b4ea  jz      short loc_18002B551
0x18002b4ec  cmp     [rdx], r14w
0x18002b4f0  jz      short loc_18002B551
0x18002b4f2  test    r8d, r8d
0x18002b4f5  jz      short loc_18002B551
0x18002b4f7  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002b4fc  mov     ebx, eax
0x18002b4fe  test    eax, eax
0x18002b500  js      short loc_18002B54D
0x18002b502  mov     rdx, rbp; struct _SECURITY_ATTRIBUTES *
0x18002b505  mov     [rdi+3Ch], esi
0x18002b508  mov     rcx, rdi; this
0x18002b50b  call    ?InstantiatePipe@MULTI_IPM@@AEAAJPEAU_SECURITY_ATTRIBUTES@@@Z; MULTI_IPM::InstantiatePipe(_SECURITY_ATTRIBUTES *)
0x18002b510  mov     ebx, eax
0x18002b512  test    eax, eax
0x18002b514  jns     short loc_18002B54D
0x18002b516  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002b51d  jz      short loc_18002B54D
0x18002b51f  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002b526  lea     r9, aMultiIpmCreate_0; "MULTI_IPM::CreateServer"
0x18002b52d  mov     dword ptr [rsp+58h+var_30], eax; char
0x18002b531  lea     r8d, [r14+3Eh]; unsigned int
0x18002b535  lea     rax, aMultiIpmCreate; "MULTI_IPM::CreateServer failed Instanti"...
0x18002b53c  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b543  mov     [rsp+58h+var_38], rax; char *
0x18002b548  call    PuDbgPrint
0x18002b54d  mov     eax, ebx
0x18002b54f  jmp     short loc_18002B556
0x18002b551  mov     eax, 80070057h
0x18002b556  add     rsp, 30h
0x18002b55a  pop     r14
0x18002b55c  pop     rdi
0x18002b55d  pop     rsi
0x18002b55e  pop     rbp
0x18002b55f  pop     rbx
0x18002b560  retn
```
