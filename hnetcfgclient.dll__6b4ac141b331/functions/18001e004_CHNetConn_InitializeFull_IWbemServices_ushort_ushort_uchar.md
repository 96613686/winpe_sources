# CHNetConn::InitializeFull(IWbemServices *,ushort *,ushort *,uchar)

- ea: `0x18001e004`
- end: `0x18001e128`
- name: `?InitializeFull@CHNetConn@@QEAAJPEAUIWbemServices@@PEAG1E@Z`
- size: `292`
- prototype: `int(CHNetConn *__hidden this, struct IWbemServices *, unsigned __int16 *, unsigned __int16 *, unsigned __int8)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001a820`
- `0x18001b2c0`
- `0x1800203b0`
- `0x180020930`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18001e004`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001e06c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e080`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e06c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e080`

## pseudocode

```c
__int64 __fastcall CHNetConn::InitializeFull(
        CHNetConn *this,
        struct IWbemServices *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int8 a5)
{
  BSTR v9; // rax
  unsigned int v10; // ebx
  BSTR v11; // rax
  PVOID *v12; // rcx
  __int64 v13; // rdx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
  }
  *((_QWORD *)this + 8) = a2;
  ((void (__fastcall *)(struct IWbemServices *))a2->lpVtbl->AddRef)(a2);
  *((_BYTE *)this + 96) = a5;
  v9 = SysAllocString(a3);
  *((_QWORD *)this + 9) = v9;
  if ( !v9 )
  {
    v10 = -2147024882;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v10;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_17;
    v13 = 38;
    goto LABEL_15;
  }
  v10 = 0;
  v11 = SysAllocString(a4);
  *((_QWORD *)this + 10) = v11;
  if ( v11 )
  {
LABEL_16:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_17;
  }
  v10 = -2147024882;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 37;
LABEL_15:
    WPP_SF_d(v12[2], v13, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, 2147942414LL);
    goto LABEL_16;
  }
LABEL_17:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 && *((_BYTE *)v12 + 25) >= 6u )
    WPP_SF_d(v12[2], 39, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18001e004  push    rbx
0x18001e006  push    rbp
0x18001e007  push    rsi
0x18001e008  push    rdi
0x18001e009  push    r15
0x18001e00b  sub     rsp, 20h
0x18001e00f  mov     rsi, r9
0x18001e012  mov     rbp, r8
0x18001e015  mov     rbx, rdx
0x18001e018  mov     rdi, rcx
0x18001e01b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e022  lea     r15, WPP_GLOBAL_Control
0x18001e029  cmp     rcx, r15
0x18001e02c  jz      short loc_18001E04F
0x18001e02e  test    byte ptr [rcx+1Ch], 8
0x18001e032  jz      short loc_18001E04F
0x18001e034  cmp     byte ptr [rcx+19h], 6
0x18001e038  jb      short loc_18001E04F
0x18001e03a  mov     rcx, [rcx+10h]
0x18001e03e  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001e045  mov     edx, 24h ; '$'
0x18001e04a  call    WPP_SF_
0x18001e04f  mov     [rdi+40h], rbx
0x18001e053  mov     rcx, rbx
0x18001e056  mov     rax, [rbx]
0x18001e059  mov     rax, [rax+8]
0x18001e05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e062  mov     al, [rsp+48h+arg_20]
0x18001e066  mov     rcx, rbp; psz
0x18001e069  mov     [rdi+60h], al
0x18001e06c  call    cs:__imp_SysAllocString
0x18001e072  mov     [rdi+48h], rax
0x18001e076  test    rax, rax
0x18001e079  jz      short loc_18001E0B5
0x18001e07b  mov     rcx, rsi; psz
0x18001e07e  xor     ebx, ebx
0x18001e080  call    cs:__imp_SysAllocString
0x18001e086  mov     [rdi+50h], rax
0x18001e08a  test    rax, rax
0x18001e08d  jnz     short loc_18001E0EB
0x18001e08f  mov     r9d, 8007000Eh
0x18001e095  mov     ebx, r9d
0x18001e098  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e09f  cmp     rcx, r15
0x18001e0a2  jz      short loc_18001E11B
0x18001e0a4  test    byte ptr [rcx+1Ch], 8
0x18001e0a8  jz      short loc_18001E0F2
0x18001e0aa  cmp     byte ptr [rcx+19h], 2
0x18001e0ae  jb      short loc_18001E0F2
0x18001e0b0  lea     edx, [rax+25h]
0x18001e0b3  jmp     short loc_18001E0DB
0x18001e0b5  mov     r9d, 8007000Eh
0x18001e0bb  mov     ebx, r9d
0x18001e0be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0c5  cmp     rcx, r15
0x18001e0c8  jz      short loc_18001E11B
0x18001e0ca  test    byte ptr [rcx+1Ch], 8
0x18001e0ce  jz      short loc_18001E0F2
0x18001e0d0  cmp     byte ptr [rcx+19h], 2
0x18001e0d4  jb      short loc_18001E0F2
0x18001e0d6  mov     edx, 26h ; '&'
0x18001e0db  mov     rcx, [rcx+10h]
0x18001e0df  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001e0e6  call    WPP_SF_d
0x18001e0eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0f2  cmp     rcx, r15
0x18001e0f5  jz      short loc_18001E11B
0x18001e0f7  test    byte ptr [rcx+1Ch], 8
0x18001e0fb  jz      short loc_18001E11B
0x18001e0fd  cmp     byte ptr [rcx+19h], 6
0x18001e101  jb      short loc_18001E11B
0x18001e103  mov     rcx, [rcx+10h]
0x18001e107  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001e10e  mov     edx, 27h ; '''
0x18001e113  mov     r9d, ebx
0x18001e116  call    WPP_SF_d
0x18001e11b  mov     eax, ebx
0x18001e11d  add     rsp, 20h
0x18001e121  pop     r15
0x18001e123  pop     rdi
0x18001e124  pop     rsi
0x18001e125  pop     rbp
0x18001e126  pop     rbx
0x18001e127  retn
```
