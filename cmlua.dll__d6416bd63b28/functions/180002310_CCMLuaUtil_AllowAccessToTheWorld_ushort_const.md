# CCMLuaUtil::AllowAccessToTheWorld(ushort const *)

- ea: `0x180002310`
- end: `0x18000240f`
- name: `?AllowAccessToTheWorld@CCMLuaUtil@@UEAAJPEBG@Z`
- size: `255`
- prototype: `__int64 __fastcall(CCMLuaUtil *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002144`
- `0x180002310`
- `0x1800035ec`
- `0x180005486`
- `0x180006010`

## import_xrefs

- `cmutil!CmFree` at `0x1800023df`
- `cmutil!CmFree` at `0x1800023df`
- `KERNEL32!FreeLibrary` at `0x1800023ee`
- `KERNEL32!FreeLibrary` at `0x1800023ee`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::AllowAccessToTheWorld(CCMLuaUtil *this, const unsigned __int16 *a2)
{
  BOOL v3; // ebx
  const char *v4; // rdx
  const char **v5; // r8
  unsigned int v7; // [rsp+20h] [rbp-69h]
  __int64 v8; // [rsp+40h] [rbp-49h] BYREF
  HMODULE hLibModule; // [rsp+50h] [rbp-39h] BYREF
  void *v10[17]; // [rsp+58h] [rbp-31h] BYREF
  int v11; // [rsp+F8h] [rbp+6Fh] BYREF
  int v12; // [rsp+100h] [rbp+77h] BYREF
  void *v13; // [rsp+108h] [rbp+7Fh] BYREF

  v3 = 0;
  if ( a2 && *a2 )
  {
    memset_0(&hLibModule, 0, 0x68u);
    if ( (unsigned int)LinkToDll(&hLibModule, v4, v5, v10, v7) )
    {
      v13 = 0;
      if ( !AllocateSecurityDescriptorAllowAccessToWorld(&v13, (struct _AdvapiLinkageStruct *)&hLibModule) )
      {
        if ( v13 )
        {
          v12 = 0;
          v11 = 0;
          v8 = 0;
          if ( ((unsigned int (__fastcall *)(void *, int *, __int64 *, int *))v10[9])(v13, &v12, &v8, &v11) )
            v3 = ((__int64 (__fastcall *)(const unsigned __int16 *, __int64, __int64, _QWORD, _QWORD, __int64, _QWORD))v10[10])(
                   a2,
                   1,
                   4,
                   0,
                   0,
                   v8,
                   0) == 0;
        }
      }
      CmFree(v13);
    }
    if ( hLibModule )
      FreeLibrary(hLibModule);
  }
  return !v3 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180002310  push    rbp
0x180002312  push    rbx
0x180002313  push    rsi
0x180002314  push    r14
0x180002316  push    r15
0x180002318  lea     rbp, [rsp-37h]
0x18000231d  sub     rsp, 0C0h
0x180002324  mov     rsi, rdx
0x180002327  xor     r15d, r15d
0x18000232a  mov     ebx, r15d
0x18000232d  test    rdx, rdx
0x180002330  jz      loc_1800023F5
0x180002336  cmp     [rdx], r15w
0x18000233a  jz      loc_1800023F5
0x180002340  xor     edx, edx; Val
0x180002342  lea     r8d, [r15+68h]; Size
0x180002346  lea     rcx, [rbp+57h+hLibModule]; void *
0x18000234a  call    memset_0
0x18000234f  lea     r9, [rbp+57h+var_88]; void **
0x180002353  lea     rcx, [rbp+57h+hLibModule]; HINSTANCE *
0x180002357  call    ?LinkToDll@@YAHPEAPEAUHINSTANCE__@@PEBDPEAPEBDQEAPEAXK@Z; LinkToDll(HINSTANCE__ * *,char const *,char const * *,void * * const,ulong)
0x18000235c  test    eax, eax
0x18000235e  jz      loc_1800023E5
0x180002364  mov     [rbp+57h+arg_18], r15
0x180002368  lea     rdx, [rbp+57h+hLibModule]; struct _AdvapiLinkageStruct *
0x18000236c  lea     rcx, [rbp+57h+arg_18]; void **
0x180002370  call    ?AllocateSecurityDescriptorAllowAccessToWorld@@YAKPEAPEAXPEAU_AdvapiLinkageStruct@@@Z; AllocateSecurityDescriptorAllowAccessToWorld(void * *,_AdvapiLinkageStruct *)
0x180002375  test    eax, eax
0x180002377  jnz     short loc_1800023DB
0x180002379  cmp     [rbp+57h+arg_18], r15
0x18000237d  jz      short loc_1800023DB
0x18000237f  mov     [rbp+57h+arg_10], r15d
0x180002383  mov     [rbp+57h+arg_8], r15d
0x180002387  mov     [rbp+57h+var_A0], r15
0x18000238b  lea     r9, [rbp+57h+arg_8]
0x18000238f  lea     r8, [rbp+57h+var_A0]
0x180002393  lea     rdx, [rbp+57h+arg_10]
0x180002397  mov     rcx, [rbp+57h+arg_18]
0x18000239b  mov     rax, [rbp+57h+var_40]
0x18000239f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023a4  test    eax, eax
0x1800023a6  jz      short loc_1800023DB
0x1800023a8  mov     [rsp+0E0h+var_B0], r15
0x1800023ad  mov     rcx, [rbp+57h+var_A0]
0x1800023b1  mov     [rsp+0E0h+var_B8], rcx
0x1800023b6  mov     [rsp+0E0h+var_C0], r15
0x1800023bb  xor     r9d, r9d
0x1800023be  lea     r8d, [r15+4]
0x1800023c2  lea     r14d, [r15+1]
0x1800023c6  mov     edx, r14d
0x1800023c9  mov     rcx, rsi
0x1800023cc  mov     rax, [rbp+57h+var_38]
0x1800023d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023d5  test    eax, eax
0x1800023d7  cmovz   ebx, r14d
0x1800023db  mov     rcx, [rbp+57h+arg_18]
0x1800023df  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x1800023e5  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x1800023e9  test    rcx, rcx
0x1800023ec  jz      short loc_1800023F5
0x1800023ee  call    cs:__imp_FreeLibrary
0x1800023f4  nop
0x1800023f5  neg     ebx
0x1800023f7  sbb     eax, eax
0x1800023f9  not     eax
0x1800023fb  and     eax, 80004005h
0x180002400  add     rsp, 0C0h
0x180002407  pop     r15
0x180002409  pop     r14
0x18000240b  pop     rsi
0x18000240c  pop     rbx
0x18000240d  pop     rbp
0x18000240e  retn
```
