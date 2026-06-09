# CSession::RecordHr(long,VAR *,ushort const *,long)

- ea: `0x18003477c`
- end: `0x180034977`
- name: `?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z`
- size: `507`
- prototype: `__int64 __fastcall(CSession *__hidden this, int, struct VAR *, const unsigned __int16 *Src, int)`
- caller_count: `56`
- callee_count: `10`
- tags: ``

## callers

- `0x1800054f4`
- `0x18000599c`
- `0x180007e9c`
- `0x18000826c`
- `0x180023440`
- `0x1800336c0`
- `0x180033c70`
- `0x180034690`
- `0x180040b6c`
- `0x18004ef8c`
- `0x18004f578`
- `0x18005d250`
- `0x18005d2d0`
- `0x18005d350`
- `0x18005d3d0`
- `0x18005d450`
- `0x18005d4d0`
- `0x18005d550`
- `0x18005d5d0`
- `0x18005d650`
- `0x18005d6d0`
- `0x18005d750`
- `0x18005d7d0`
- `0x18005d850`
- `0x18005d8d0`
- `0x18005d950`
- `0x18005d9d0`
- `0x18005da50`
- `0x18005dad0`
- `0x18005db60`
- `0x18005dbe0`
- `0x18005dc70`
- `0x18005dd00`
- `0x18005dd90`
- `0x18005de20`
- `0x18005deb0`
- `0x18005df40`
- `0x18005dfd0`
- `0x18005e050`
- `0x18005e0e0`
- `0x18005e170`
- `0x18005e200`
- `0x18005e290`
- `0x18005e320`
- `0x18005e3b0`
- `0x18005e440`
- `0x18005e4d0`
- `0x18005e550`
- `0x18005e5d0`
- `0x18005e650`

## callees

- `0x18000796c`
- `0x180007d04`
- `0x180007d80`
- `0x180007da4`
- `0x180007dc8`
- `0x180007e68`
- `0x18003477c`
- `0x180096692`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `msvcrt!free` at `0x1800348a9`
- `msvcrt!free` at `0x1800348a9`
- `OLEAUT32!__imp_SysFreeString` at `0x180034943`
- `OLEAUT32!__imp_SysFreeString` at `0x180034943`

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
0x18003477c  push    rbx
0x18003477e  push    rbp
0x18003477f  push    rsi
0x180034780  push    rdi
0x180034781  push    r12
0x180034783  push    r14
0x180034785  push    r15
0x180034787  sub     rsp, 440h
0x18003478e  mov     rax, cs:__security_cookie
0x180034795  xor     rax, rsp
0x180034798  mov     [rsp+478h+var_48], rax
0x1800347a0  mov     r14d, [rsp+478h+arg_20]
0x1800347a8  mov     rbx, rcx
0x1800347ab  mov     ecx, edx; int
0x1800347ad  mov     rsi, r8
0x1800347b0  mov     rbp, r9
0x1800347b3  mov     r8d, edx
0x1800347b6  call    ?AlreadyRecorded@@YAHJ@Z; AlreadyRecorded(long)
0x1800347bb  xor     r12d, r12d
0x1800347be  test    eax, eax
0x1800347c0  jnz     loc_18003496F
0x1800347c6  mov     edx, ecx; int
0x1800347c8  movzx   r15d, r8w
0x1800347cc  mov     rcx, rbx; this
0x1800347cf  call    ?RecordError@CSession@@QEAAJJ@Z; CSession::RecordError(long)
0x1800347d4  mov     r8d, eax
0x1800347d7  cmp     eax, 86664004h
0x1800347dc  jnz     loc_18003496F
0x1800347e2  mov     rdi, [rbx+440h]
0x1800347e9  test    rdi, rdi
0x1800347ec  jnz     short loc_1800347F5
0x1800347ee  lea     rdi, [rbx+448h]
0x1800347f5  mov     rcx, [rbx+50h]; this
0x1800347f9  test    rcx, rcx
0x1800347fc  jz      loc_1800348B5
0x180034802  test    rsi, rsi
0x180034805  jz      loc_180034958
0x18003480b  mov     r9d, r14d; int
0x18003480e  mov     r8, rbp; Src
0x180034811  mov     rdx, rsi; struct VAR *
0x180034814  call    ?PszGetVarName@CScriptRuntime@@QEAAPEAGPEAVVAR@@PEBGJ@Z; CScriptRuntime::PszGetVarName(VAR *,ushort const *,long)
0x180034819  mov     rbp, rax
0x18003481c  test    rax, rax
0x18003481f  jz      loc_1800348B5
0x180034825  mov     rcx, rbx; this
0x180034828  call    ?GetUserLocale@CSession@@QEAAKXZ; CSession::GetUserLocale(void)
0x18003482d  lea     ecx, [r15+2710h]; int
0x180034834  mov     r9d, eax; unsigned int
0x180034837  mov     r8d, 0FAh; int
0x18003483d  lea     rdx, [rsp+478h+var_248]; unsigned __int16 *
0x180034845  call    ?FGetResourceString@@YAHJPEAGHKH@Z; FGetResourceString(long,ushort *,int,ulong,int)
0x18003484a  test    eax, eax
0x18003484c  jz      short loc_1800348A6
0x18003484e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180034852  mov     rsi, rbx
0x180034855  inc     rsi
0x180034858  cmp     [rbp+rsi*2+0], r12w
0x18003485e  jnz     short loc_180034855
0x180034860  movzx   edx, [rsp+478h+var_248]
0x180034868  lea     rcx, [rsp+478h+var_448]; void *
0x18003486d  lea     r14, [rsp+478h+var_246]
0x180034875  cmp     r12w, dx
0x180034879  jnz     short loc_1800348DD
0x18003487b  mov     [rcx], r12w
0x18003487f  lea     rax, [rsp+478h+var_448]
0x180034884  inc     rbx
0x180034887  cmp     [rax+rbx*2], r12w
0x18003488c  jnz     short loc_180034884
0x18003488e  mov     edx, ebx; unsigned int
0x180034890  lea     rcx, [rsp+478h+var_448]; unsigned __int16 *
0x180034895  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18003489a  mov     rbx, rax
0x18003489d  test    rax, rax
0x1800348a0  jnz     loc_18003492E
0x1800348a6  mov     rcx, rbp; Block
0x1800348a9  call    cs:__imp_free
0x1800348b0  nop     dword ptr [rax+rax+00h]
0x1800348b5  mov     eax, 86664004h
0x1800348ba  mov     rcx, [rsp+478h+var_48]
0x1800348c2  xor     rcx, rsp; StackCookie
0x1800348c5  call    __security_check_cookie
0x1800348ca  add     rsp, 440h
0x1800348d1  pop     r15
0x1800348d3  pop     r14
0x1800348d5  pop     r12
0x1800348d7  pop     rdi
0x1800348d8  pop     rsi
0x1800348d9  pop     rbp
0x1800348da  pop     rbx
0x1800348db  retn
0x1800348dd  lea     rax, [rsp+478h+var_256]
0x1800348e5  cmp     rcx, rax
0x1800348e8  jnb     short loc_18003487B
0x1800348ea  mov     eax, 7Ch ; '|'
0x1800348ef  cmp     ax, dx
0x1800348f2  jz      short loc_180034908
0x1800348f4  mov     [rcx], dx
0x1800348f7  add     rcx, 2
0x1800348fb  movzx   edx, word ptr [r14]
0x1800348ff  add     r14, 2
0x180034903  jmp     loc_180034875
0x180034908  lea     r8, [rsi+rsi]; Size
0x18003490c  lea     r15, [r8+rcx]
0x180034910  lea     rax, [rsp+478h+var_256]
0x180034918  cmp     r15, rax
0x18003491b  jnb     loc_18003487B
0x180034921  mov     rdx, rbp; Src
0x180034924  call    memcpy_0
0x180034929  mov     rcx, r15
0x18003492c  jmp     short loc_1800348FB
0x18003492e  mov     rax, [rdi+38h]
0x180034932  lea     rcx, [rdi+8]
0x180034936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003493b  mov     rcx, [rdi+18h]; bstrString
0x18003493f  mov     [rdi+38h], r12
0x180034943  call    cs:__imp_SysFreeString
0x18003494a  nop     dword ptr [rax+rax+00h]
0x18003494f  mov     [rdi+18h], rbx
0x180034953  jmp     loc_1800348A6
0x180034958  test    rbp, rbp
0x18003495b  jnz     loc_18003480B
0x180034961  test    r14d, r14d
0x180034964  js      loc_1800348B5
0x18003496a  jmp     loc_18003480B
0x18003496f  mov     eax, r8d
0x180034972  jmp     loc_1800348BA
```
