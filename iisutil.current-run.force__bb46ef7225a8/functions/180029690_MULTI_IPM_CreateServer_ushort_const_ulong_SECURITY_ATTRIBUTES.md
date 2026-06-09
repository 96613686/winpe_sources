# MULTI_IPM::CreateServer(ushort const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180029690`
- end: `0x180029721`
- name: `?CreateServer@MULTI_IPM@@QEAAJPEBGKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(MULTI_IPM *__hidden this, const unsigned __int16 *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001b60`
- `0x180007300`
- `0x180029690`
- `0x180029730`

## string_xrefs

- `0x1800296f5`: `MULTI_IPM::CreateServer failed InstantiatePipe hr=0x%08x \n `
- `0x1800296e6`: `MULTI_IPM::CreateServer`
- `0x1800296fc`: `servercommon\inetsrv\iis\iisrearc\core\common\util\multi_ipm.cxx`

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
0x180029690  push    rbx
0x180029692  push    rbp
0x180029693  push    rsi
0x180029694  push    rdi
0x180029695  push    r14
0x180029697  sub     rsp, 30h
0x18002969b  xor     r14d, r14d
0x18002969e  mov     rbp, r9
0x1800296a1  mov     esi, r8d
0x1800296a4  mov     rdi, rcx
0x1800296a7  test    rdx, rdx
0x1800296aa  jz      short loc_180029711
0x1800296ac  cmp     [rdx], r14w
0x1800296b0  jz      short loc_180029711
0x1800296b2  test    r8d, r8d
0x1800296b5  jz      short loc_180029711
0x1800296b7  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800296bc  mov     ebx, eax
0x1800296be  test    eax, eax
0x1800296c0  js      short loc_18002970D
0x1800296c2  mov     rdx, rbp; struct _SECURITY_ATTRIBUTES *
0x1800296c5  mov     [rdi+3Ch], esi
0x1800296c8  mov     rcx, rdi; this
0x1800296cb  call    ?InstantiatePipe@MULTI_IPM@@AEAAJPEAU_SECURITY_ATTRIBUTES@@@Z; MULTI_IPM::InstantiatePipe(_SECURITY_ATTRIBUTES *)
0x1800296d0  mov     ebx, eax
0x1800296d2  test    eax, eax
0x1800296d4  jns     short loc_18002970D
0x1800296d6  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800296dd  jz      short loc_18002970D
0x1800296df  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800296e6  lea     r9, aMultiIpmCreate_0; "MULTI_IPM::CreateServer"
0x1800296ed  mov     dword ptr [rsp+58h+var_30], eax; char
0x1800296f1  lea     r8d, [r14+3Eh]; unsigned int
0x1800296f5  lea     rax, aMultiIpmCreate; "MULTI_IPM::CreateServer failed Instanti"...
0x1800296fc  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029703  mov     [rsp+58h+var_38], rax; char *
0x180029708  call    PuDbgPrint
0x18002970d  mov     eax, ebx
0x18002970f  jmp     short loc_180029716
0x180029711  mov     eax, 80070057h
0x180029716  add     rsp, 30h
0x18002971a  pop     r14
0x18002971c  pop     rdi
0x18002971d  pop     rsi
0x18002971e  pop     rbp
0x18002971f  pop     rbx
0x180029720  retn
```
