# CMSDiscRecorderObj::GetPath(ushort * *)

- ea: `0x18000f520`
- end: `0x18000f65c`
- name: `?GetPath@CMSDiscRecorderObj@@UEAAJPEAPEAG@Z`
- size: `316`
- prototype: `__int64 __fastcall(CMSDiscRecorderObj *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180007d40`
- `0x180007d80`
- `0x18000f520`
- `0x180010714`
- `0x1800127ec`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000f5f5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f5f5`

## pseudocode

```c
__int64 __fastcall CMSDiscRecorderObj::GetPath(CMSDiscRecorderObj *this, unsigned __int16 **a2)
{
  _QWORD *v4; // rcx
  char *v5; // rdi
  int v6; // ebx
  int v7; // eax
  unsigned __int16 *v8; // rax
  _DWORD v10[4]; // [rsp+30h] [rbp-B8h] BYREF
  OLECHAR psz[64]; // [rsp+40h] [rbp-A8h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids, (char *)this - 8);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = (char *)this - 8;
  v10[0] = 0;
  if ( *((_BYTE *)this + 140) )
  {
    if ( a2 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)this + 9) + 168LL))(*((_QWORD *)this + 9), v10);
      if ( v7 >= 0 )
      {
        v6 = StringCchPrintfW(psz, 0x40u, L"\\Device\\CdRom%d", v10[0]);
        if ( v6 >= 0 )
        {
          v8 = SysAllocString(psz);
          *a2 = v8;
          if ( !v8 )
            v6 = -2147024882;
        }
      }
      else
      {
        v6 = TranslateIMAPI2Error((unsigned int)v7);
      }
      v4 = WPP_GLOBAL_Control;
    }
    else
    {
      v6 = -2147467261;
    }
  }
  else
  {
    v6 = -2147220980;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 1) != 0 )
    WPP_SF_qD(v4[7], 25, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids, v5, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000f520  mov     [rsp+arg_10], rbx
0x18000f525  push    rbp
0x18000f526  push    rsi
0x18000f527  push    rdi
0x18000f528  sub     rsp, 0D0h
0x18000f52f  mov     rax, cs:__security_cookie
0x18000f536  xor     rax, rsp
0x18000f539  mov     [rsp+0E8h+var_28], rax
0x18000f541  mov     rsi, rdx
0x18000f544  mov     rbx, rcx
0x18000f547  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f54e  lea     rbp, WPP_GLOBAL_Control
0x18000f555  cmp     rcx, rbp
0x18000f558  jz      short loc_18000F580
0x18000f55a  test    byte ptr [rcx+44h], 1
0x18000f55e  jz      short loc_18000F580
0x18000f560  mov     rcx, [rcx+38h]
0x18000f564  lea     r9, [rbx-8]
0x18000f568  mov     edx, 18h
0x18000f56d  lea     r8, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids
0x18000f574  call    WPP_SF_q
0x18000f579  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f580  lea     rdi, [rbx-8]
0x18000f584  mov     [rsp+0E8h+var_B8], 0
0x18000f58c  cmp     byte ptr [rdi+94h], 0
0x18000f593  jnz     short loc_18000F59C
0x18000f595  mov     ebx, 8004020Ch
0x18000f59a  jmp     short loc_18000F610
0x18000f59c  test    rsi, rsi
0x18000f59f  jnz     short loc_18000F5A8
0x18000f5a1  mov     ebx, 80004003h
0x18000f5a6  jmp     short loc_18000F610
0x18000f5a8  mov     rcx, [rbx+48h]
0x18000f5ac  lea     rdx, [rsp+0E8h+var_B8]
0x18000f5b1  mov     rax, [rcx]
0x18000f5b4  mov     rax, [rax+0A8h]
0x18000f5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5c0  test    eax, eax
0x18000f5c2  jns     short loc_18000F5CF
0x18000f5c4  mov     ecx, eax
0x18000f5c6  call    TranslateIMAPI2Error
0x18000f5cb  mov     ebx, eax
0x18000f5cd  jmp     short loc_18000F609
0x18000f5cf  mov     r9d, [rsp+0E8h+var_B8]
0x18000f5d4  lea     r8, aDeviceCdromD; "\\Device\\CdRom%d"
0x18000f5db  mov     edx, 40h ; '@'; unsigned __int64
0x18000f5e0  lea     rcx, [rsp+0E8h+psz]; unsigned __int16 *
0x18000f5e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f5ea  mov     ebx, eax
0x18000f5ec  test    eax, eax
0x18000f5ee  js      short loc_18000F609
0x18000f5f0  lea     rcx, [rsp+0E8h+psz]; psz
0x18000f5f5  call    cs:__imp_SysAllocString
0x18000f5fb  test    rax, rax
0x18000f5fe  mov     [rsi], rax
0x18000f601  mov     ecx, 8007000Eh
0x18000f606  cmovz   ebx, ecx
0x18000f609  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f610  cmp     rcx, rbp
0x18000f613  jz      short loc_18000F637
0x18000f615  test    byte ptr [rcx+44h], 1
0x18000f619  jz      short loc_18000F637
0x18000f61b  mov     rcx, [rcx+38h]
0x18000f61f  lea     r8, WPP_d26c5e076d373d9f44765f33302aa61b_Traceguids
0x18000f626  mov     edx, 19h
0x18000f62b  mov     [rsp+0E8h+var_C8], ebx
0x18000f62f  mov     r9, rdi
0x18000f632  call    WPP_SF_qD
0x18000f637  mov     eax, ebx
0x18000f639  mov     rcx, [rsp+0E8h+var_28]
0x18000f641  xor     rcx, rsp; StackCookie
0x18000f644  call    __security_check_cookie
0x18000f649  mov     rbx, [rsp+0E8h+arg_10]
0x18000f651  add     rsp, 0D0h
0x18000f658  pop     rdi
0x18000f659  pop     rsi
0x18000f65a  pop     rbp
0x18000f65b  retn
```
