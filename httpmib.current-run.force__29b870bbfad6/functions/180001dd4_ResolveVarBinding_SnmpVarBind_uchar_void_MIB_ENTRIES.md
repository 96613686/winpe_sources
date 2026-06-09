# ResolveVarBinding(SnmpVarBind *,uchar,void *,_MIB_ENTRIES *)

- ea: `0x180001dd4`
- end: `0x18000201c`
- name: `?ResolveVarBinding@@YAIPEAUSnmpVarBind@@EPEAXPEAU_MIB_ENTRIES@@@Z`
- size: `584`
- prototype: `unsigned int __fastcall(AsnObjectIdentifier *pOidDst, unsigned __int8, void *, struct _MIB_ENTRIES *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001a40`

## callees

- `0x180001b5c`
- `0x180001d10`
- `0x180001dd4`
- `0x180004010`

## import_xrefs

- `snmpapi!SnmpUtilOidCpy` at `0x180001e84`
- `snmpapi!SnmpUtilOidCpy` at `0x180001f4b`
- `snmpapi!SnmpUtilOidCpy` at `0x180001e84`
- `snmpapi!SnmpUtilOidCpy` at `0x180001f4b`
- `snmpapi!SnmpUtilOidFree` at `0x180001ebf`
- `snmpapi!SnmpUtilOidFree` at `0x180001f3b`
- `snmpapi!SnmpUtilOidFree` at `0x180001ebf`
- `snmpapi!SnmpUtilOidFree` at `0x180001f3b`
- `snmpapi!SnmpUtilOidAppend` at `0x180001e92`
- `snmpapi!SnmpUtilOidAppend` at `0x180001f57`
- `snmpapi!SnmpUtilOidAppend` at `0x180001e92`
- `snmpapi!SnmpUtilOidAppend` at `0x180001f57`
- `snmpapi!SnmpUtilOidCmp` at `0x180001eb2`
- `snmpapi!SnmpUtilOidCmp` at `0x180001eb2`
- `iisutil!PuDbgPrint` at `0x180001e52`
- `iisutil!PuDbgPrint` at `0x180001f05`
- `iisutil!PuDbgPrint` at `0x180002003`
- `iisutil!PuDbgPrint` at `0x180001e52`
- `iisutil!PuDbgPrint` at `0x180001f05`
- `iisutil!PuDbgPrint` at `0x180002003`

## string_xrefs

- `0x180001e41`: `servercommon\inetsrv\iis\iisrearc\core\snmp\dll\mib.cxx`
- `0x180001ef3`: `servercommon\inetsrv\iis\iisrearc\core\snmp\dll\mib.cxx`
- `0x180001ffc`: `servercommon\inetsrv\iis\iisrearc\core\snmp\dll\mib.cxx`
- `0x180001edc`: ` Comparing with suffix Oid  %08x yields %d\n`

## pseudocode

```c
__int64 __fastcall ResolveVarBinding(
        AsnObjectIdentifier *pOidDst,
        unsigned __int8 a2,
        void *a3,
        struct _MIB_ENTRIES *a4)
{
  AsnObjectIdentifier *v4; // rbx
  int v5; // r14d
  unsigned __int8 v8; // r15
  AsnObjectIdentifier *v9; // r12
  unsigned int v10; // edi
  INT v11; // ebp
  char v12; // al
  __int64 (__fastcall *v13)(AsnObjectIdentifier *, _QWORD, AsnObjectIdentifier *, AsnObjectIdentifier **, void *); // rax
  unsigned int NextVar; // eax
  AsnObjectIdentifier pOidDsta; // [rsp+40h] [rbp-58h] BYREF

  v4 = off_180007830;
  *(_QWORD *)&pOidDsta.idLength = 0;
  v5 = 0;
  HIDWORD(pOidDsta.ids) = 0;
  v8 = a2;
  v9 = (AsnObjectIdentifier *)((char *)off_180007830 + 40 * dword_180007828);
  if ( (g_dwDebugFlags & 0x2000000) != 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\snmp\\dll\\mib.cxx",
        133,
        "ResolveVarBinding",
        " ResolveVarBinding( Var=%08x, Action=%x) called.\n",
        (_DWORD)pOidDst,
        a2);
    PrintAsnObjectIdentifier(" Variable to Resolve", pOidDst);
    v4 = off_180007830;
  }
  v10 = 2;
  while ( v4 < v9 )
  {
    SnmpUtilOidCpy(&pOidDsta, off_180007820);
    SnmpUtilOidAppend(&pOidDsta, v4);
    if ( pOidDsta.idLength && !pOidDsta.ids )
      goto LABEL_21;
    v11 = SnmpUtilOidCmp(pOidDst, &pOidDsta);
    SnmpUtilOidFree(&pOidDsta);
    if ( (g_dwDebugFlags & 0x2000000) != 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\snmp\\dll\\mib.cxx",
          168,
          "ResolveVarBinding",
          " Comparing with suffix Oid  %08x yields %d\n",
          (_DWORD)v4,
          v11);
      PrintAsnObjectIdentifier(" StatisticsSuffix", v4);
    }
    if ( !v11 )
      goto LABEL_22;
    if ( v11 < 0 )
    {
      if ( v8 == 0xA1 )
      {
        SnmpUtilOidFree(pOidDst);
        SnmpUtilOidCpy(pOidDst, off_180007820);
        SnmpUtilOidAppend(pOidDst, v4);
        v12 = BYTE4(v4[2].ids);
        if ( v12 != 68 && v12 != 48 )
          v8 = -96;
      }
      else
      {
LABEL_21:
        v5 = 2;
      }
LABEL_22:
      if ( v4 >= v9 )
        break;
      if ( v5 )
      {
        v10 = v5;
      }
      else
      {
        v13 = *(__int64 (__fastcall **)(AsnObjectIdentifier *, _QWORD, AsnObjectIdentifier *, AsnObjectIdentifier **, void *))&v4[2].idLength;
        if ( v13 )
        {
          NextVar = v13(pOidDst, v8, v4, &off_180007820, a3);
        }
        else
        {
          if ( v8 != 0xA1 )
            break;
          NextVar = MibGetNextVar(pOidDst);
        }
        v10 = NextVar;
      }
      break;
    }
    v4 = (AsnObjectIdentifier *)((char *)v4 + 40);
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x2000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\snmp\\dll\\mib.cxx",
      262,
      "ResolveVarBinding",
      " ResolveVarBinding returns %u.\n",
      v10);
  return v10;
}

```

## disassembly

```asm
0x180001dd4  mov     r11, rsp
0x180001dd7  push    rbx
0x180001dd8  push    rbp
0x180001dd9  push    rsi
0x180001dda  push    rdi
0x180001ddb  push    r12
0x180001ddd  push    r13
0x180001ddf  push    r14
0x180001de1  push    r15
0x180001de3  sub     rsp, 58h
0x180001de7  mov     rbx, cs:off_180007830
0x180001dee  xor     eax, eax
0x180001df0  mov     [r11-58h], rax
0x180001df4  xor     r14d, r14d
0x180001df7  mov     dword ptr [rsp+98h+pOidDst.ids+4], eax
0x180001dfb  mov     r13, r8
0x180001dfe  movsxd  rax, cs:dword_180007828
0x180001e05  mov     rsi, rcx
0x180001e08  movzx   r15d, dl
0x180001e0c  lea     r9, [rax+rax*4]
0x180001e10  mov     eax, cs:g_dwDebugFlags
0x180001e16  lea     r12, [rbx+r9*8]
0x180001e1a  bt      eax, 19h
0x180001e1e  jnb     short loc_180001E6E
0x180001e20  test    al, 3
0x180001e22  jz      short loc_180001E58
0x180001e24  mov     [r11-68h], r15d
0x180001e28  lea     rax, aResolvevarbind_1; " ResolveVarBinding( Var=%08x, Action=%x"...
0x180001e2f  mov     [r11-70h], rcx
0x180001e33  lea     r9, aResolvevarbind_0; "ResolveVarBinding"
0x180001e3a  mov     rcx, cs:g_pDebug
0x180001e41  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180001e48  mov     r8d, 85h
0x180001e4e  mov     [r11-78h], rax
0x180001e52  call    cs:__imp_PuDbgPrint
0x180001e58  mov     rdx, rsi
0x180001e5b  lea     rcx, aVariableToReso; " Variable to Resolve"
0x180001e62  call    PrintAsnObjectIdentifier
0x180001e67  mov     rbx, cs:off_180007830
0x180001e6e  mov     edi, 2
0x180001e73  jmp     loc_180001F24
0x180001e78  mov     rdx, cs:off_180007820; pOidSrc
0x180001e7f  lea     rcx, [rsp+98h+pOidDst]; pOidDst
0x180001e84  call    cs:__imp_SnmpUtilOidCpy
0x180001e8a  mov     rdx, rbx; pOidSrc
0x180001e8d  lea     rcx, [rsp+98h+pOidDst]; pOidDst
0x180001e92  call    cs:__imp_SnmpUtilOidAppend
0x180001e98  cmp     [rsp+98h+pOidDst.idLength], r14d
0x180001e9d  jbe     short loc_180001EAA
0x180001e9f  cmp     [rsp+44h], r14
0x180001ea4  jz      loc_180001F6D
0x180001eaa  lea     rdx, [rsp+98h+pOidDst]; pOid2
0x180001eaf  mov     rcx, rsi; pOid1
0x180001eb2  call    cs:__imp_SnmpUtilOidCmp
0x180001eb8  lea     rcx, [rsp+98h+pOidDst]; pOid
0x180001ebd  mov     ebp, eax
0x180001ebf  call    cs:__imp_SnmpUtilOidFree
0x180001ec5  mov     eax, cs:g_dwDebugFlags
0x180001ecb  bt      eax, 19h
0x180001ecf  jnb     short loc_180001F1A
0x180001ed1  test    al, 3
0x180001ed3  jz      short loc_180001F0B
0x180001ed5  mov     rcx, cs:g_pDebug
0x180001edc  lea     rax, aComparingWithS; " Comparing with suffix Oid  %08x yields"...
0x180001ee3  mov     [rsp+98h+var_68], ebp
0x180001ee7  lea     r9, aResolvevarbind_0; "ResolveVarBinding"
0x180001eee  mov     [rsp+98h+var_70], rbx
0x180001ef3  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180001efa  mov     r8d, 0A8h
0x180001f00  mov     [rsp+98h+var_78], rax
0x180001f05  call    cs:__imp_PuDbgPrint
0x180001f0b  mov     rdx, rbx
0x180001f0e  lea     rcx, aStatisticssuff; " StatisticsSuffix"
0x180001f15  call    PrintAsnObjectIdentifier
0x180001f1a  test    ebp, ebp
0x180001f1c  jz      short loc_180001F70
0x180001f1e  js      short loc_180001F32
0x180001f20  add     rbx, 28h ; '('
0x180001f24  cmp     rbx, r12
0x180001f27  jb      loc_180001E78
0x180001f2d  jmp     loc_180001FC2
0x180001f32  cmp     r15b, 0A1h
0x180001f36  jnz     short loc_180001F6D
0x180001f38  mov     rcx, rsi; pOid
0x180001f3b  call    cs:__imp_SnmpUtilOidFree
0x180001f41  mov     rdx, cs:off_180007820; pOidSrc
0x180001f48  mov     rcx, rsi; pOidDst
0x180001f4b  call    cs:__imp_SnmpUtilOidCpy
0x180001f51  mov     rdx, rbx; pOidSrc
0x180001f54  mov     rcx, rsi; pOidDst
0x180001f57  call    cs:__imp_SnmpUtilOidAppend
0x180001f5d  mov     al, [rbx+20h]
0x180001f60  cmp     al, 44h ; 'D'
0x180001f62  jz      short loc_180001F70
0x180001f64  cmp     al, 30h ; '0'
0x180001f66  jz      short loc_180001F70
0x180001f68  mov     r15b, 0A0h
0x180001f6b  jmp     short loc_180001F70
0x180001f6d  mov     r14d, edi
0x180001f70  cmp     rbx, r12
0x180001f73  jnb     short loc_180001FC2
0x180001f75  test    r14d, r14d
0x180001f78  jnz     short loc_180001FBF
0x180001f7a  mov     rax, [rbx+18h]
0x180001f7e  test    rax, rax
0x180001f81  jnz     short loc_180001FA2
0x180001f83  cmp     r15b, 0A1h
0x180001f87  jnz     short loc_180001FC2
0x180001f89  mov     r9, r13
0x180001f8c  lea     r8, off_180007820
0x180001f93  mov     rdx, rbx
0x180001f96  mov     rcx, rsi; pOidDst
0x180001f99  call    MibGetNextVar
0x180001f9e  mov     edi, eax
0x180001fa0  jmp     short loc_180001FC2
0x180001fa2  movzx   edx, r15b
0x180001fa6  lea     r9, off_180007820
0x180001fad  mov     r8, rbx
0x180001fb0  mov     [rsp+98h+var_78], r13
0x180001fb5  mov     rcx, rsi
0x180001fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fbd  jmp     short loc_180001F9E
0x180001fbf  mov     edi, r14d
0x180001fc2  mov     eax, cs:g_dwDebugFlags
0x180001fc8  test    al, 3
0x180001fca  setnz   cl
0x180001fcd  bt      eax, 19h
0x180001fd1  setb    al
0x180001fd4  test    al, cl
0x180001fd6  jz      short loc_180002009
0x180001fd8  mov     rcx, cs:g_pDebug
0x180001fdf  lea     rax, aResolvevarbind; " ResolveVarBinding returns %u.\n"
0x180001fe6  mov     dword ptr [rsp+98h+var_70], edi
0x180001fea  lea     r9, aResolvevarbind_0; "ResolveVarBinding"
0x180001ff1  mov     r8d, 106h
0x180001ff7  mov     [rsp+98h+var_78], rax
0x180001ffc  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180002003  call    cs:__imp_PuDbgPrint
0x180002009  mov     eax, edi
0x18000200b  add     rsp, 58h
0x18000200f  pop     r15
0x180002011  pop     r14
0x180002013  pop     r13
0x180002015  pop     r12
0x180002017  pop     rdi
0x180002018  pop     rsi
0x180002019  pop     rbp
0x18000201a  pop     rbx
0x18000201b  retn
```
