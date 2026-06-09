# CSession::RecordHr(long,VAR *,ushort const *,long)

- ea: `0x180006bf0`
- end: `0x180006dde`
- name: `?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z`
- size: `494`
- prototype: `__int64 __fastcall(CSession *__hidden this, int, struct VAR *, const unsigned __int16 *Src, int)`
- caller_count: `56`
- callee_count: `10`
- tags: ``

## callers

- `0x180005b48`
- `0x1800060f0`
- `0x180006b10`
- `0x180006ed8`
- `0x18000ad6c`
- `0x18000b130`
- `0x180016894`
- `0x180026230`
- `0x18003229c`
- `0x1800409cc`
- `0x18004e65c`
- `0x18005c0e0`
- `0x18005c160`
- `0x18005c1e0`
- `0x18005c260`
- `0x18005c2e0`
- `0x18005c360`
- `0x18005c3e0`
- `0x18005c460`
- `0x18005c4e0`
- `0x18005c560`
- `0x18005c5e0`
- `0x18005c660`
- `0x18005c6e0`
- `0x18005c760`
- `0x18005c7e0`
- `0x18005c860`
- `0x18005c8e0`
- `0x18005c960`
- `0x18005c9f0`
- `0x18005ca70`
- `0x18005cb00`
- `0x18005cb90`
- `0x18005cc20`
- `0x18005ccb0`
- `0x18005cd40`
- `0x18005cdd0`
- `0x18005ce60`
- `0x18005cee0`
- `0x18005cf70`
- `0x18005cff0`
- `0x18005d080`
- `0x18005d110`
- `0x18005d1a0`
- `0x18005d230`
- `0x18005d2c0`
- `0x18005d350`
- `0x18005d3d0`
- `0x18005d450`
- `0x18005d4d0`

## callees

- `0x180006bf0`
- `0x18000a864`
- `0x18000abe4`
- `0x18000ac5c`
- `0x18000ac7c`
- `0x18000aca0`
- `0x18000ad40`
- `0x180094282`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `msvcrt!free` at `0x180006d1d`
- `msvcrt!free` at `0x180006d1d`
- `OLEAUT32!__imp_SysFreeString` at `0x180006db0`
- `OLEAUT32!__imp_SysFreeString` at `0x180006db0`

## pseudocode

```c
__int64 __fastcall CSession::RecordHr(CSession *this, int a2, struct VAR *a3, const unsigned __int16 *Src, int a5)
{
  int v8; // ecx
  unsigned int v9; // r8d
  int v10; // r15d
  char *v11; // rdi
  CScriptRuntime *v12; // rcx
  unsigned __int16 *VarName; // rbp
  unsigned int UserLocale; // eax
  __int64 v15; // rbx
  __int64 v16; // rsi
  unsigned __int16 v17; // dx
  unsigned __int16 *v18; // rcx
  unsigned __int16 *v19; // r14
  unsigned __int16 *v20; // rbx
  unsigned __int16 *v22; // r15
  OLECHAR *v23; // rcx
  int v24; // [rsp+20h] [rbp-458h]
  unsigned __int16 v25[249]; // [rsp+30h] [rbp-448h] BYREF
  unsigned __int16 v26[7]; // [rsp+222h] [rbp-256h] BYREF
  unsigned __int16 v27; // [rsp+230h] [rbp-248h] BYREF
  char v28; // [rsp+232h] [rbp-246h] BYREF

  if ( (unsigned int)AlreadyRecorded(a2) )
    return v9;
  v10 = (unsigned __int16)v9;
  v9 = CSession::RecordError(this, v8);
  if ( v9 != -2040119292 )
    return v9;
  v11 = (char *)*((_QWORD *)this + 136);
  if ( !v11 )
    v11 = (char *)this + 1096;
  v12 = (CScriptRuntime *)*((_QWORD *)this + 10);
  if ( v12 && (a3 || Src || a5 >= 0) )
  {
    VarName = CScriptRuntime::PszGetVarName(v12, a3, Src, a5);
    if ( VarName )
    {
      UserLocale = CSession::GetUserLocale(this);
      if ( FGetResourceString(v10 + 10000, &v27, 250, UserLocale, v24) )
      {
        v15 = -1;
        v16 = -1;
        do
          ++v16;
        while ( VarName[v16] );
        v17 = v27;
        v18 = v25;
        v19 = (unsigned __int16 *)&v28;
        while ( v17 && v18 < v26 )
        {
          if ( v17 == 124 )
          {
            v22 = &v18[v16];
            if ( v22 >= v26 )
              break;
            memcpy_0(v18, VarName, 2 * v16);
            v18 = v22;
          }
          else
          {
            *v18++ = v17;
          }
          v17 = *v19++;
        }
        *v18 = 0;
        do
          ++v15;
        while ( v25[v15] );
        v20 = _SysAllocStringLen(v25, v15);
        if ( v20 )
        {
          (*((void (__fastcall **)(char *))v11 + 7))(v11 + 8);
          v23 = (OLECHAR *)*((_QWORD *)v11 + 3);
          *((_QWORD *)v11 + 7) = 0;
          SysFreeString(v23);
          *((_QWORD *)v11 + 3) = v20;
        }
      }
      free(VarName);
    }
  }
  return 2254848004LL;
}

```

## disassembly

```asm
0x180006bf0  push    rbx
0x180006bf2  push    rbp
0x180006bf3  push    rsi
0x180006bf4  push    rdi
0x180006bf5  push    r12
0x180006bf7  push    r14
0x180006bf9  push    r15
0x180006bfb  sub     rsp, 440h
0x180006c02  mov     rax, cs:__security_cookie
0x180006c09  xor     rax, rsp
0x180006c0c  mov     [rsp+478h+var_48], rax
0x180006c14  mov     r14d, [rsp+478h+arg_20]
0x180006c1c  mov     rbx, rcx
0x180006c1f  mov     ecx, edx; int
0x180006c21  mov     rsi, r8
0x180006c24  mov     rbp, r9
0x180006c27  mov     r8d, edx
0x180006c2a  call    ?AlreadyRecorded@@YAHJ@Z; AlreadyRecorded(long)
0x180006c2f  xor     r12d, r12d
0x180006c32  test    eax, eax
0x180006c34  jnz     loc_180006DD6
0x180006c3a  mov     edx, ecx; int
0x180006c3c  movzx   r15d, r8w
0x180006c40  mov     rcx, rbx; this
0x180006c43  call    ?RecordError@CSession@@QEAAJJ@Z; CSession::RecordError(long)
0x180006c48  mov     r8d, eax
0x180006c4b  cmp     eax, 86664004h
0x180006c50  jnz     loc_180006DD6
0x180006c56  mov     rdi, [rbx+440h]
0x180006c5d  test    rdi, rdi
0x180006c60  jnz     short loc_180006C69
0x180006c62  lea     rdi, [rbx+448h]
0x180006c69  mov     rcx, [rbx+50h]; this
0x180006c6d  test    rcx, rcx
0x180006c70  jz      loc_180006D23
0x180006c76  test    rsi, rsi
0x180006c79  jz      loc_180006DBF
0x180006c7f  mov     r9d, r14d; int
0x180006c82  mov     r8, rbp; Src
0x180006c85  mov     rdx, rsi; struct VAR *
0x180006c88  call    ?PszGetVarName@CScriptRuntime@@QEAAPEAGPEAVVAR@@PEBGJ@Z; CScriptRuntime::PszGetVarName(VAR *,ushort const *,long)
0x180006c8d  mov     rbp, rax
0x180006c90  test    rax, rax
0x180006c93  jz      loc_180006D23
0x180006c99  mov     rcx, rbx; this
0x180006c9c  call    ?GetUserLocale@CSession@@QEAAKXZ; CSession::GetUserLocale(void)
0x180006ca1  lea     ecx, [r15+2710h]; int
0x180006ca8  mov     r9d, eax; unsigned int
0x180006cab  mov     r8d, 0FAh; int
0x180006cb1  lea     rdx, [rsp+478h+var_248]; unsigned __int16 *
0x180006cb9  call    ?FGetResourceString@@YAHJPEAGHKH@Z; FGetResourceString(long,ushort *,int,ulong,int)
0x180006cbe  test    eax, eax
0x180006cc0  jz      short loc_180006D1A
0x180006cc2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006cc6  mov     rsi, rbx
0x180006cc9  inc     rsi
0x180006ccc  cmp     [rbp+rsi*2+0], r12w
0x180006cd2  jnz     short loc_180006CC9
0x180006cd4  movzx   edx, [rsp+478h+var_248]
0x180006cdc  lea     rcx, [rsp+478h+var_448]; void *
0x180006ce1  lea     r14, [rsp+478h+var_246]
0x180006ce9  cmp     r12w, dx
0x180006ced  jnz     short loc_180006D4A
0x180006cef  mov     [rcx], r12w
0x180006cf3  lea     rax, [rsp+478h+var_448]
0x180006cf8  inc     rbx
0x180006cfb  cmp     [rax+rbx*2], r12w
0x180006d00  jnz     short loc_180006CF8
0x180006d02  mov     edx, ebx; unsigned int
0x180006d04  lea     rcx, [rsp+478h+var_448]; unsigned __int16 *
0x180006d09  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x180006d0e  mov     rbx, rax
0x180006d11  test    rax, rax
0x180006d14  jnz     loc_180006D9B
0x180006d1a  mov     rcx, rbp; Block
0x180006d1d  call    cs:__imp_free
0x180006d23  mov     eax, 86664004h
0x180006d28  mov     rcx, [rsp+478h+var_48]
0x180006d30  xor     rcx, rsp; StackCookie
0x180006d33  call    __security_check_cookie
0x180006d38  add     rsp, 440h
0x180006d3f  pop     r15
0x180006d41  pop     r14
0x180006d43  pop     r12
0x180006d45  pop     rdi
0x180006d46  pop     rsi
0x180006d47  pop     rbp
0x180006d48  pop     rbx
0x180006d49  retn
0x180006d4a  lea     rax, [rsp+478h+var_256]
0x180006d52  cmp     rcx, rax
0x180006d55  jnb     short loc_180006CEF
0x180006d57  mov     eax, 7Ch ; '|'
0x180006d5c  cmp     ax, dx
0x180006d5f  jz      short loc_180006D75
0x180006d61  mov     [rcx], dx
0x180006d64  add     rcx, 2
0x180006d68  movzx   edx, word ptr [r14]
0x180006d6c  add     r14, 2
0x180006d70  jmp     loc_180006CE9
0x180006d75  lea     r8, [rsi+rsi]; Size
0x180006d79  lea     r15, [r8+rcx]
0x180006d7d  lea     rax, [rsp+478h+var_256]
0x180006d85  cmp     r15, rax
0x180006d88  jnb     loc_180006CEF
0x180006d8e  mov     rdx, rbp; Src
0x180006d91  call    memcpy_0
0x180006d96  mov     rcx, r15
0x180006d99  jmp     short loc_180006D68
0x180006d9b  mov     rax, [rdi+38h]
0x180006d9f  lea     rcx, [rdi+8]
0x180006da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da8  mov     rcx, [rdi+18h]; bstrString
0x180006dac  mov     [rdi+38h], r12
0x180006db0  call    cs:__imp_SysFreeString
0x180006db6  mov     [rdi+18h], rbx
0x180006dba  jmp     loc_180006D1A
0x180006dbf  test    rbp, rbp
0x180006dc2  jnz     loc_180006C7F
0x180006dc8  test    r14d, r14d
0x180006dcb  js      loc_180006D23
0x180006dd1  jmp     loc_180006C7F
0x180006dd6  mov     eax, r8d
0x180006dd9  jmp     loc_180006D28
```
