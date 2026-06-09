# CMSMQQueueInfo::Create(tagVARIANT *,tagVARIANT *)

- ea: `0x18001cb50`
- end: `0x18001ccd5`
- name: `?Create@CMSMQQueueInfo@@UEAAJPEAUtagVARIANT@@0@Z`
- size: `389`
- prototype: `int(CMSMQQueueInfo *__hidden this, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000178c`
- `0x180005430`
- `0x18000cb34`
- `0x18001cb50`
- `0x18001cd7c`
- `0x18001d17c`
- `0x18001d774`
- `0x180026934`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001ccb0`
- `KERNEL32!LeaveCriticalSection` at `0x18001ccb0`
- `OLEAUT32!__imp_SysReAllocString` at `0x18001cc67`
- `OLEAUT32!__imp_SysReAllocString` at `0x18001cc67`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001cbfa`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001cbfa`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cc98`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cc98`
- `mqrt!MQCreateQueue` at `0x18001cc3e`
- `mqrt!MQCreateQueue` at `0x18001cc3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQQueueInfo::Create(CMSMQQueueInfo *this, struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  WCHAR *v6; // rsi
  int Bool; // r15d
  int v8; // edi
  int v9; // ebx
  _OWORD *v10; // rcx
  HRESULT v11; // eax
  unsigned int ErrorHelper; // ebx
  MQQUEUEPROPS pQueueProps; // [rsp+30h] [rbp-50h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v16; // [rsp+70h] [rbp-10h]
  UINT ui; // [rsp+B0h] [rbp+30h] BYREF
  void *Block; // [rsp+C8h] [rbp+48h] BYREF

  CCriticalSection::Lock((CMSMQQueueInfo *)((char *)this + 72));
  memset(&pQueueProps, 0, sizeof(pQueueProps));
  ui = 1024;
  v6 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v16 = 0;
  Block = 0;
  Bool = GetBool(a2);
  v8 = GetBool(a3);
  v9 = CMSMQQueueInfo::CreateQueueProps(
         (CMSMQQueueInfo *)((char *)this - 8),
         1,
         0xBu,
         &pQueueProps,
         Bool,
         &qword_18002F9F0);
  if ( v9 >= 0 )
  {
    v6 = SysAllocStringLen(0, ui);
    if ( v6 )
    {
      if ( v8 )
      {
        if ( !(unsigned int)GetWorldReadableSecurityDescriptor(pSecurityDescriptor, (ACL **)&Block) )
        {
          v9 = -1072824287;
          goto LABEL_15;
        }
        v10 = pSecurityDescriptor;
      }
      else
      {
        v10 = 0;
      }
      v11 = MQCreateQueue(v10, &pQueueProps, v6, &ui);
      v9 = v11;
      if ( v11 < 0 )
        goto LABEL_15;
      if ( v11 == 1074659329 && *((_DWORD *)this + 59) )
        v9 = 0;
      if ( SysReAllocString((BSTR *)this + 19, v6) )
      {
        *((_DWORD *)this + 40) = 1;
        *((_DWORD *)this + 44) = Bool;
        goto LABEL_15;
      }
    }
    v9 = -2147024882;
  }
LABEL_15:
  operator delete(Block);
  CMSMQQueueInfo::FreeQueueProps(&pQueueProps);
  SysFreeString(v6);
  ErrorHelper = CreateErrorHelper((unsigned int)v9, 4);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  return ErrorHelper;
}

```

## disassembly

```asm
0x18001cb50  mov     [rsp-28h+arg_8], rbx
0x18001cb55  mov     [rsp-28h+arg_10], rsi
0x18001cb5a  push    rbp
0x18001cb5b  push    rdi
0x18001cb5c  push    r12
0x18001cb5e  push    r14
0x18001cb60  push    r15
0x18001cb62  mov     rbp, rsp
0x18001cb65  sub     rsp, 80h
0x18001cb6c  mov     rdi, r8
0x18001cb6f  mov     rbx, rdx
0x18001cb72  mov     r14, rcx
0x18001cb75  add     rcx, 48h ; 'H'; this
0x18001cb79  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001cb7e  mov     qword ptr [rbp+pQueueProps.cProp], 0
0x18001cb86  xorps   xmm0, xmm0
0x18001cb89  movdqu  xmmword ptr [rbp+pQueueProps.aPropID], xmm0
0x18001cb8e  mov     [rbp+pQueueProps.aStatus], 0
0x18001cb96  mov     [rbp+ui], 400h
0x18001cb9d  xor     esi, esi
0x18001cb9f  xor     eax, eax
0x18001cba1  movups  [rbp+pSecurityDescriptor], xmm0
0x18001cba5  movups  [rbp+var_20], xmm0
0x18001cba9  mov     [rbp+var_10], rax
0x18001cbad  mov     [rbp+Block], rax
0x18001cbb1  mov     rcx, rbx; struct tagVARIANT *
0x18001cbb4  call    ?GetBool@@YAHPEAUtagVARIANT@@@Z; GetBool(tagVARIANT *)
0x18001cbb9  mov     r15d, eax
0x18001cbbc  mov     rcx, rdi; struct tagVARIANT *
0x18001cbbf  call    ?GetBool@@YAHPEAUtagVARIANT@@@Z; GetBool(tagVARIANT *)
0x18001cbc4  mov     edi, eax
0x18001cbc6  lea     rcx, [r14-8]; this
0x18001cbca  lea     rax, qword_18002F9F0
0x18001cbd1  mov     [rsp+80h+var_58], rax; unsigned int *
0x18001cbd6  mov     [rsp+80h+var_60], r15d; int
0x18001cbdb  lea     r9, [rbp+pQueueProps]; struct tagMQQUEUEPROPS *
0x18001cbdf  lea     edx, [rsi+1]; int
0x18001cbe2  lea     r8d, [rsi+0Bh]; unsigned int
0x18001cbe6  call    ?CreateQueueProps@CMSMQQueueInfo@@IEAAJHIPEAUtagMQQUEUEPROPS@@HQEBK@Z; CMSMQQueueInfo::CreateQueueProps(int,uint,tagMQQUEUEPROPS *,int,ulong const * const)
0x18001cbeb  mov     ebx, eax
0x18001cbed  test    eax, eax
0x18001cbef  js      loc_18001CC83
0x18001cbf5  mov     edx, [rbp+ui]; ui
0x18001cbf8  xor     ecx, ecx; strIn
0x18001cbfa  call    cs:__imp_SysAllocStringLen
0x18001cc00  mov     rsi, rax
0x18001cc03  test    rax, rax
0x18001cc06  jnz     short loc_18001CC0F
0x18001cc08  mov     ebx, 8007000Eh
0x18001cc0d  jmp     short loc_18001CC83
0x18001cc0f  test    edi, edi
0x18001cc11  jz      short loc_18001CC31
0x18001cc13  lea     rdx, [rbp+Block]
0x18001cc17  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18001cc1b  call    GetWorldReadableSecurityDescriptor
0x18001cc20  test    eax, eax
0x18001cc22  jnz     short loc_18001CC2B
0x18001cc24  mov     ebx, 0C00E0021h
0x18001cc29  jmp     short loc_18001CC83
0x18001cc2b  lea     rcx, [rbp+pSecurityDescriptor]
0x18001cc2f  jmp     short loc_18001CC33
0x18001cc31  xor     ecx, ecx; pSecurityDescriptor
0x18001cc33  lea     r9, [rbp+ui]; lpdwFormatNameLength
0x18001cc37  mov     r8, rsi; lpwcsFormatName
0x18001cc3a  lea     rdx, [rbp+pQueueProps]; pQueueProps
0x18001cc3e  call    cs:__imp_MQCreateQueue
0x18001cc44  mov     ebx, eax
0x18001cc46  test    eax, eax
0x18001cc48  js      short loc_18001CC83
0x18001cc4a  cmp     eax, 400E0001h
0x18001cc4f  jnz     short loc_18001CC5D
0x18001cc51  xor     eax, eax
0x18001cc53  cmp     [r14+0ECh], eax
0x18001cc5a  cmovnz  ebx, eax
0x18001cc5d  lea     rcx, [r14+98h]; pbstr
0x18001cc64  mov     rdx, rsi; psz
0x18001cc67  call    cs:__imp_SysReAllocString
0x18001cc6d  test    eax, eax
0x18001cc6f  jz      short loc_18001CC08
0x18001cc71  mov     dword ptr [r14+0A0h], 1
0x18001cc7c  mov     [r14+0B0h], r15d
0x18001cc83  mov     rcx, [rbp+Block]; Block
0x18001cc87  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cc8c  lea     rcx, [rbp+pQueueProps]; struct tagMQQUEUEPROPS *
0x18001cc90  call    ?FreeQueueProps@CMSMQQueueInfo@@KAXPEAUtagMQQUEUEPROPS@@@Z; CMSMQQueueInfo::FreeQueueProps(tagMQQUEUEPROPS *)
0x18001cc95  mov     rcx, rsi; bstrString
0x18001cc98  call    cs:__imp_SysFreeString
0x18001cc9e  mov     edx, 4
0x18001cca3  mov     ecx, ebx
0x18001cca5  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001ccaa  mov     ebx, eax
0x18001ccac  lea     rcx, [r14+48h]; lpCriticalSection
0x18001ccb0  call    cs:__imp_LeaveCriticalSection
0x18001ccb6  nop
0x18001ccb7  mov     eax, ebx
0x18001ccb9  lea     r11, [rsp+80h+var_s0]
0x18001ccc1  mov     rbx, [r11+38h]
0x18001ccc5  mov     rsi, [r11+40h]
0x18001ccc9  mov     rsp, r11
0x18001cccc  pop     r15
0x18001ccce  pop     r14
0x18001ccd0  pop     r12
0x18001ccd2  pop     rdi
0x18001ccd3  pop     rbp
0x18001ccd4  retn
```
