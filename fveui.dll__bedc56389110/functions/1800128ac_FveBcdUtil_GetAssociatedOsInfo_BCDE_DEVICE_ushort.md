# FveBcdUtil::GetAssociatedOsInfo(_BCDE_DEVICE * *,ushort * *)

- ea: `0x1800128ac`
- end: `0x1800129d4`
- name: `?GetAssociatedOsInfo@FveBcdUtil@@SAJPEAPEAU_BCDE_DEVICE@@PEAPEAG@Z`
- size: `296`
- prototype: `__int64 __fastcall(struct _BCDE_DEVICE **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001167c`

## callees

- `0x180001bb0`
- `0x1800022d8`
- `0x18000ff64`
- `0x1800126b8`
- `0x1800128ac`
- `0x1800129dc`

## import_xrefs

- `bcd!BcdOpenSystemStore` at `0x1800128f6`
- `bcd!BcdOpenSystemStore` at `0x1800128f6`
- `bcd!BcdOpenObject` at `0x180012935`
- `bcd!BcdOpenObject` at `0x180012935`
- `bcd!BcdCloseObject` at `0x1800129a6`
- `bcd!BcdCloseObject` at `0x18002c894`
- `bcd!BcdCloseObject` at `0x1800129a6`
- `bcd!BcdCloseObject` at `0x18002c894`
- `bcd!BcdCloseStore` at `0x1800129b1`
- `bcd!BcdCloseStore` at `0x18002c89e`
- `bcd!BcdCloseStore` at `0x1800129b1`
- `bcd!BcdCloseStore` at `0x18002c89e`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::GetAssociatedOsInfo(struct _BCDE_DEVICE **a1, unsigned __int16 **a2)
{
  NTSTATUS v3; // eax
  signed int AssociatedOs; // ebx
  NTSTATUS v5; // eax
  void *v6; // rcx
  void *v8; // [rsp+28h] [rbp-50h] BYREF
  void *Block; // [rsp+30h] [rbp-48h] BYREF
  void *v10; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v11; // [rsp+40h] [rbp-38h] BYREF
  __int64 v12; // [rsp+48h] [rbp-30h]
  struct _GUID v13; // [rsp+50h] [rbp-28h] BYREF

  v13 = 0;
  v8 = 0;
  v10 = 0;
  Block = 0;
  v12 = 0;
  v3 = BcdOpenSystemStore(&v8, a2);
  AssociatedOs = FromNtStatus(v3);
  if ( AssociatedOs >= 0 )
  {
    AssociatedOs = FveBcdUtil::GetAssociatedOs(v8, &v13);
    if ( AssociatedOs >= 0 )
    {
      v5 = BcdOpenObject(v8, &v13, &v10);
      AssociatedOs = FromNtStatus(v5);
      if ( AssociatedOs >= 0 )
      {
        AssociatedOs = FveBcdUtil::GetBcdElementData(v10, 0x11000001u, &Block, &v11);
        if ( AssociatedOs >= 0 )
        {
          *a1 = (struct _BCDE_DEVICE *)Block;
          Block = 0;
        }
      }
    }
  }
  if ( Block )
    operator delete(Block);
  v6 = v8;
  if ( v8 )
  {
    if ( v10 )
    {
      BcdCloseObject(v10);
      v6 = v8;
    }
    BcdCloseStore(v6);
  }
  return (unsigned int)AssociatedOs;
}

```

## disassembly

```asm
0x1800128ac  mov     r11, rsp
0x1800128af  mov     [r11+10h], rbx
0x1800128b3  push    rdi
0x1800128b4  sub     rsp, 70h
0x1800128b8  mov     rax, cs:__security_cookie
0x1800128bf  xor     rax, rsp
0x1800128c2  mov     [rsp+78h+var_18], rax
0x1800128c7  mov     rdi, rcx
0x1800128ca  xorps   xmm0, xmm0
0x1800128cd  movups  xmmword ptr [rsp+78h+var_28.Data1], xmm0
0x1800128d2  mov     qword ptr [r11-50h], 0
0x1800128da  mov     qword ptr [r11-40h], 0
0x1800128e2  mov     qword ptr [r11-48h], 0
0x1800128ea  mov     qword ptr [r11-30h], 0
0x1800128f2  lea     rcx, [r11-50h]
0x1800128f6  call    cs:__imp_BcdOpenSystemStore
0x1800128fc  mov     ecx, eax; int
0x1800128fe  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180012903  mov     ebx, eax
0x180012905  mov     [rsp+78h+var_58], eax
0x180012909  test    eax, eax
0x18001290b  js      short loc_180012980
0x18001290d  lea     rdx, [rsp+78h+var_28]; struct _GUID *
0x180012912  mov     rcx, [rsp+78h+var_50]; void *
0x180012917  call    ?GetAssociatedOs@FveBcdUtil@@SAJPEAXPEAU_GUID@@@Z; FveBcdUtil::GetAssociatedOs(void *,_GUID *)
0x18001291c  mov     ebx, eax
0x18001291e  mov     [rsp+78h+var_58], eax
0x180012922  test    eax, eax
0x180012924  js      short loc_180012980
0x180012926  lea     r8, [rsp+78h+var_40]
0x18001292b  lea     rdx, [rsp+78h+var_28]
0x180012930  mov     rcx, [rsp+78h+var_50]
0x180012935  call    cs:__imp_BcdOpenObject
0x18001293b  mov     ecx, eax; int
0x18001293d  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180012942  mov     ebx, eax
0x180012944  mov     [rsp+78h+var_58], eax
0x180012948  test    eax, eax
0x18001294a  js      short loc_180012980
0x18001294c  lea     r9, [rsp+78h+var_38]; unsigned int *
0x180012951  lea     r8, [rsp+78h+Block]; void **
0x180012956  mov     edx, 11000001h; unsigned int
0x18001295b  mov     rcx, [rsp+78h+var_40]; void *
0x180012960  call    ?GetBcdElementData@FveBcdUtil@@SAJPEAXKPEAPEAXPEAK@Z; FveBcdUtil::GetBcdElementData(void *,ulong,void * *,ulong *)
0x180012965  mov     ebx, eax
0x180012967  mov     [rsp+78h+var_58], eax
0x18001296b  test    eax, eax
0x18001296d  js      short loc_180012980
0x18001296f  mov     rax, [rsp+78h+Block]
0x180012974  mov     [rdi], rax
0x180012977  mov     [rsp+78h+Block], 0
0x180012980  mov     rcx, [rsp+78h+Block]; Block
0x180012985  test    rcx, rcx
0x180012988  jz      short loc_18001298F
0x18001298a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001298f  mov     rcx, [rsp+78h+var_50]
0x180012994  test    rcx, rcx
0x180012997  jz      short loc_1800129B7
0x180012999  mov     rax, [rsp+78h+var_40]
0x18001299e  test    rax, rax
0x1800129a1  jz      short loc_1800129B1
0x1800129a3  mov     rcx, rax
0x1800129a6  call    cs:__imp_BcdCloseObject
0x1800129ac  mov     rcx, [rsp+78h+var_50]
0x1800129b1  call    cs:__imp_BcdCloseStore
0x1800129b7  mov     eax, ebx
0x1800129b9  mov     rcx, [rsp+78h+var_18]
0x1800129be  xor     rcx, rsp; StackCookie
0x1800129c1  call    __security_check_cookie
0x1800129c6  mov     rbx, [rsp+78h+arg_8]
0x1800129ce  add     rsp, 70h
0x1800129d2  pop     rdi
0x1800129d3  retn
0x18002c858  push    rbp
0x18002c85a  sub     rsp, 20h
0x18002c85e  mov     rbp, rdx
0x18002c861  mov     rcx, [rbp+30h]; Block
0x18002c865  test    rcx, rcx
0x18002c868  jz      short loc_18002C870
0x18002c86a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c86f  nop
0x18002c870  mov     rcx, [rbp+48h]; Block
0x18002c874  test    rcx, rcx
0x18002c877  jz      short loc_18002C87F
0x18002c879  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c87e  nop
0x18002c87f  mov     rcx, [rbp+28h]
0x18002c883  test    rcx, rcx
0x18002c886  jz      short loc_18002C8A5
0x18002c888  mov     rax, [rbp+38h]
0x18002c88c  test    rax, rax
0x18002c88f  jz      short loc_18002C89E
0x18002c891  mov     rcx, rax
0x18002c894  call    cs:__imp_BcdCloseObject
0x18002c89a  mov     rcx, [rbp+28h]
0x18002c89e  call    cs:__imp_BcdCloseStore
0x18002c8a4  nop
0x18002c8a5  add     rsp, 20h
0x18002c8a9  pop     rbp
0x18002c8aa  retn
```
