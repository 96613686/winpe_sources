# FveBcdUtil::GetAssociatedOs(void *,_GUID *)

- ea: `0x1800126b8`
- end: `0x1800128a3`
- name: `?GetAssociatedOs@FveBcdUtil@@SAJPEAXPEAU_GUID@@@Z`
- size: `491`
- prototype: `__int64 __fastcall(void *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800128ac`

## callees

- `0x180001bb0`
- `0x1800022d8`
- `0x1800037a0`
- `0x18000ff64`
- `0x180010ad8`
- `0x1800126b8`
- `0x1800129dc`
- `0x180012b74`
- `0x1800137d8`

## import_xrefs

- `bcd!BcdOpenObject` at `0x18001276a`
- `bcd!BcdOpenObject` at `0x18001276a`
- `bcd!BcdCloseObject` at `0x180012865`
- `bcd!BcdCloseObject` at `0x18002c835`
- `bcd!BcdCloseObject` at `0x180012865`
- `bcd!BcdCloseObject` at `0x18002c835`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::GetAssociatedOs(void *a1, struct _GUID *a2)
{
  unsigned __int8 v4; // r14
  signed int DoesRegKeyExist; // ebx
  NTSTATUS v6; // eax
  NTSTATUS BcdElementData; // eax
  unsigned int v8; // esi
  unsigned int i; // edi
  struct _GUID *v10; // r12
  NTSTATUS IsAssociatedOS; // eax
  unsigned __int8 v13[4]; // [rsp+20h] [rbp-68h] BYREF
  int v14; // [rsp+24h] [rbp-64h]
  int v15; // [rsp+28h] [rbp-60h] BYREF
  unsigned int v16; // [rsp+2Ch] [rbp-5Ch] BYREF
  void *v17; // [rsp+30h] [rbp-58h] BYREF
  void *Block; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v19; // [rsp+40h] [rbp-48h]
  struct _GUID v20; // [rsp+48h] [rbp-40h] BYREF

  v20 = 0;
  v17 = 0;
  Block = 0;
  v16 = 0;
  v4 = 0;
  v13[0] = 0;
  v15 = 0;
  DoesRegKeyExist = NgscbpDoesRegKeyExist(a1, a2, &v15);
  v14 = DoesRegKeyExist;
  if ( DoesRegKeyExist >= 0 )
  {
    if ( !v15 )
    {
LABEL_3:
      DoesRegKeyExist = -2147024809;
      v14 = -2147024809;
      goto LABEL_18;
    }
    DoesRegKeyExist = FveBcdUtil::GetCurrentOsGuid(a1, &v20);
    v14 = DoesRegKeyExist;
    if ( DoesRegKeyExist >= 0 )
    {
      v6 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v17);
      DoesRegKeyExist = FromNtStatus(v6);
      v14 = DoesRegKeyExist;
      if ( DoesRegKeyExist >= 0 )
      {
        BcdElementData = FveBcdUtil::GetBcdElementData(v17, 0x24000001u, &Block, &v16);
        DoesRegKeyExist = FromNtStatus(BcdElementData);
        v14 = DoesRegKeyExist;
        if ( DoesRegKeyExist >= 0 )
        {
          if ( (v16 & 0xF) != 0 )
            goto LABEL_3;
          v8 = v16 >> 4;
          for ( i = 0; ; ++i )
          {
            v19 = i;
            if ( i >= v8 )
              break;
            v10 = (struct _GUID *)((char *)Block + 16 * i);
            IsAssociatedOS = FveBcdUtil::IsAssociatedOS(a1, v10, &v20, v13);
            DoesRegKeyExist = FromNtStatus(IsAssociatedOS);
            v14 = DoesRegKeyExist;
            if ( DoesRegKeyExist < 0 )
              goto LABEL_18;
            v4 = v13[0];
            if ( v13[0] )
            {
              *a2 = *v10;
              break;
            }
          }
          if ( !v4 )
          {
            DoesRegKeyExist = -2147024894;
            v14 = -2147024894;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                73,
                &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
                2147942402LL);
          }
        }
      }
    }
  }
LABEL_18:
  if ( v17 )
    BcdCloseObject(v17);
  if ( Block )
    operator delete(Block);
  return (unsigned int)DoesRegKeyExist;
}

```

## disassembly

```asm
0x1800126b8  mov     r11, rsp
0x1800126bb  mov     [r11+18h], rbx
0x1800126bf  mov     [r11+20h], rsi
0x1800126c3  push    rdi
0x1800126c4  push    r12
0x1800126c6  push    r13
0x1800126c8  push    r14
0x1800126ca  push    r15
0x1800126cc  sub     rsp, 60h
0x1800126d0  mov     rax, cs:__security_cookie
0x1800126d7  xor     rax, rsp
0x1800126da  mov     [rsp+88h+var_30], rax
0x1800126df  mov     r13, rdx
0x1800126e2  mov     r15, rcx
0x1800126e5  xorps   xmm0, xmm0
0x1800126e8  movups  xmmword ptr [rsp+88h+var_40.Data1], xmm0
0x1800126ed  mov     qword ptr [r11-58h], 0
0x1800126f5  mov     qword ptr [r11-50h], 0
0x1800126fd  mov     [rsp+88h+var_5C], 0
0x180012705  xor     r14b, r14b
0x180012708  mov     [r11-68h], r14b
0x18001270c  mov     [rsp+88h+var_60], 0
0x180012714  lea     r8, [r11-60h]
0x180012718  call    NgscbpDoesRegKeyExist
0x18001271d  mov     ebx, eax
0x18001271f  mov     [rsp+88h+var_64], eax
0x180012723  test    eax, eax
0x180012725  js      loc_18001285B
0x18001272b  cmp     [rsp+88h+var_60], 0
0x180012730  jnz     short loc_180012740
0x180012732  mov     ebx, 80070057h
0x180012737  mov     [rsp+88h+var_64], ebx
0x18001273b  jmp     loc_18001285B
0x180012740  lea     rdx, [rsp+88h+var_40]; struct _GUID *
0x180012745  mov     rcx, r15; void *
0x180012748  call    ?GetCurrentOsGuid@FveBcdUtil@@SAJPEAXPEAU_GUID@@@Z; FveBcdUtil::GetCurrentOsGuid(void *,_GUID *)
0x18001274d  mov     ebx, eax
0x18001274f  mov     [rsp+88h+var_64], eax
0x180012753  test    eax, eax
0x180012755  js      loc_18001285B
0x18001275b  lea     r8, [rsp+88h+var_58]
0x180012760  lea     rdx, GUID_WINDOWS_BOOTMGR
0x180012767  mov     rcx, r15
0x18001276a  call    cs:__imp_BcdOpenObject
0x180012770  mov     ecx, eax; int
0x180012772  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180012777  mov     ebx, eax
0x180012779  mov     [rsp+88h+var_64], eax
0x18001277d  test    eax, eax
0x18001277f  js      loc_18001285B
0x180012785  lea     r9, [rsp+88h+var_5C]; unsigned int *
0x18001278a  lea     r8, [rsp+88h+Block]; void **
0x18001278f  mov     edx, 24000001h; unsigned int
0x180012794  mov     rcx, [rsp+88h+var_58]; void *
0x180012799  call    ?GetBcdElementData@FveBcdUtil@@SAJPEAXKPEAPEAXPEAK@Z; FveBcdUtil::GetBcdElementData(void *,ulong,void * *,ulong *)
0x18001279e  mov     ecx, eax; int
0x1800127a0  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800127a5  mov     ebx, eax
0x1800127a7  mov     [rsp+88h+var_64], eax
0x1800127ab  test    eax, eax
0x1800127ad  js      loc_18001285B
0x1800127b3  mov     esi, [rsp+88h+var_5C]
0x1800127b7  test    sil, 0Fh
0x1800127bb  jnz     loc_180012732
0x1800127c1  shr     esi, 4
0x1800127c4  xor     edi, edi
0x1800127c6  mov     [rsp+88h+var_48], edi
0x1800127ca  cmp     edi, esi
0x1800127cc  jnb     short loc_18001281B
0x1800127ce  mov     r12d, edi
0x1800127d1  shl     r12, 4
0x1800127d5  add     r12, [rsp+88h+Block]
0x1800127da  lea     r9, [rsp+88h+var_68]; unsigned __int8 *
0x1800127df  lea     r8, [rsp+88h+var_40]; struct _GUID *
0x1800127e4  mov     rdx, r12; struct _GUID *
0x1800127e7  mov     rcx, r15; void *
0x1800127ea  call    ?IsAssociatedOS@FveBcdUtil@@SAJPEAXPEAU_GUID@@1PEAE@Z; FveBcdUtil::IsAssociatedOS(void *,_GUID *,_GUID *,uchar *)
0x1800127ef  mov     ecx, eax; int
0x1800127f1  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800127f6  mov     ebx, eax
0x1800127f8  mov     [rsp+88h+var_64], eax
0x1800127fc  test    eax, eax
0x1800127fe  js      short loc_18001285B
0x180012800  mov     r14b, [rsp+88h+var_68]
0x180012805  test    r14b, r14b
0x180012808  jz      short loc_180012817
0x18001280a  movups  xmm0, xmmword ptr [r12]
0x18001280f  movdqu  xmmword ptr [r13+0], xmm0
0x180012815  jmp     short loc_18001281B
0x180012817  inc     edi
0x180012819  jmp     short loc_1800127C6
0x18001281b  test    r14b, r14b
0x18001281e  jnz     short loc_18001285B
0x180012820  mov     ebx, 80070002h
0x180012825  mov     [rsp+88h+var_64], ebx
0x180012829  lea     rax, WPP_GLOBAL_Control
0x180012830  mov     rcx, cs:WPP_GLOBAL_Control
0x180012837  cmp     rcx, rax
0x18001283a  jz      short loc_18001285B
0x18001283c  test    byte ptr [rcx+1Ch], 2
0x180012840  jz      short loc_18001285B
0x180012842  mov     edx, 49h ; 'I'
0x180012847  mov     r9d, ebx
0x18001284a  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x180012851  mov     rcx, [rcx+10h]
0x180012855  call    WPP_SF_d
0x18001285a  nop
0x18001285b  mov     rcx, [rsp+88h+var_58]
0x180012860  test    rcx, rcx
0x180012863  jz      short loc_18001286B
0x180012865  call    cs:__imp_BcdCloseObject
0x18001286b  mov     rcx, [rsp+88h+Block]; Block
0x180012870  test    rcx, rcx
0x180012873  jz      short loc_18001287A
0x180012875  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001287a  mov     eax, ebx
0x18001287c  mov     rcx, [rsp+88h+var_30]
0x180012881  xor     rcx, rsp; StackCookie
0x180012884  call    __security_check_cookie
0x180012889  lea     r11, [rsp+88h+var_28]
0x18001288e  mov     rbx, [r11+40h]
0x180012892  mov     rsi, [r11+48h]
0x180012896  mov     rsp, r11
0x180012899  pop     r15
0x18001289b  pop     r14
0x18001289d  pop     r13
0x18001289f  pop     r12
0x1800128a1  pop     rdi
0x1800128a2  retn
0x18002c823  push    rbp
0x18002c825  sub     rsp, 20h
0x18002c829  mov     rbp, rdx
0x18002c82c  mov     rcx, [rbp+30h]
0x18002c830  test    rcx, rcx
0x18002c833  jz      short loc_18002C83C
0x18002c835  call    cs:__imp_BcdCloseObject
0x18002c83b  nop
0x18002c83c  mov     rcx, [rbp+38h]; Block
0x18002c840  test    rcx, rcx
0x18002c843  jz      short loc_18002C84B
0x18002c845  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c84a  nop
0x18002c84b  add     rsp, 20h
0x18002c84f  pop     rbp
0x18002c850  retn
```
