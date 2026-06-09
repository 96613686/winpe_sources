# CJob::UpdateJobState(int)

- ea: `0x180007640`
- end: `0x180007857`
- name: `?UpdateJobState@CJob@@QEAAJH@Z`
- size: `535`
- prototype: `__int64 __fastcall(CJob *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180004590`
- `0x18000e2ac`

## callees

- `0x1800018c0`
- `0x180007640`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800076af`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800076af`

## pseudocode

```c
int __fastcall CJob::UpdateJobState(CJob *this)
{
  int result; // eax
  int v3; // edi
  unsigned __int16 v4; // ax
  int v5; // edx
  int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned __int16 v9; // r15
  unsigned int v10; // edi
  int v11; // ebp
  int v12; // r14d
  unsigned __int16 i; // si
  int v14; // ecx
  unsigned __int16 v15; // [rsp+60h] [rbp-48h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-40h] BYREF

  if ( (*((_DWORD *)this + 22) & 0x1000000) == 0 )
  {
    *((_DWORD *)this + 21) = 267013;
    return 0;
  }
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v3 = *((_DWORD *)this + 22);
  v4 = 0;
  v15 = 0;
  if ( (v3 & 4) != 0 )
  {
    v5 = 267010;
    v6 = v3;
LABEL_5:
    v7 = v6 & 0xFFFBFFFF;
    if ( v4 || v5 == 267016 )
    {
      v8 = v7 & 0xFFBFFFFF;
      *((_DWORD *)this + 22) = v8;
      if ( (v8 & 0x1000000) != 0 )
      {
        if ( *((_WORD *)this + 48) )
          *((_DWORD *)this + 21) = 267008;
        else
          *((_DWORD *)this + 21) = 267011;
      }
    }
    else
    {
      v8 = v7 | 0x400000;
      *((_DWORD *)this + 22) = v8;
    }
    goto LABEL_28;
  }
  v9 = *((_WORD *)this + 16);
  v10 = v3 & 0x7FFF;
  v11 = 0;
  v12 = 0;
  for ( i = 0; i < v9; ++i )
  {
    result = GetTriggerRunTimes(
               (struct _TASK_TRIGGER *)(*((_QWORD *)this + 3) + 48LL * i),
               &SystemTime,
               0,
               &v15,
               1u,
               0,
               0,
               v10,
               *((_DWORD *)this + 19),
               *((_WORD *)this + 34),
               *((_WORD *)this + 35));
    v14 = result;
    if ( result < 0 )
      return result;
    v4 = v15;
    if ( v14 == 267016 )
    {
      v11 = 1;
    }
    else if ( !v14 )
    {
      v12 = 1;
      if ( v15 )
        goto LABEL_17;
    }
  }
  if ( !v12 )
  {
    v5 = (v11 != 0) + 267015;
    goto LABEL_22;
  }
LABEL_17:
  if ( v4 || !v11 )
    v5 = 0;
  else
    v5 = 267016;
LABEL_22:
  v6 = *((_DWORD *)this + 22);
  if ( v5 != 267015 )
    goto LABEL_5;
  v8 = v6 | 0x40000;
  *((_DWORD *)this + 21) = 267013;
  *((_DWORD *)this + 22) = v8;
LABEL_28:
  if ( (v8 & 4) != 0 )
    *((_DWORD *)this + 21) = 267010;
  return 0;
}

```

## disassembly

```asm
0x180007640  push    rbx
0x180007642  sub     rsp, 0A0h
0x180007649  mov     rax, cs:__security_cookie
0x180007650  xor     rax, rsp
0x180007653  mov     [rsp+0A8h+var_30], rax
0x180007658  test    dword ptr [rcx+58h], 1000000h
0x18000765f  mov     rbx, rcx
0x180007662  jnz     short loc_180007672
0x180007664  mov     dword ptr [rcx+54h], 41305h
0x18000766b  xor     eax, eax
0x18000766d  jmp     loc_180007841
0x180007672  mov     [rsp+0A8h+arg_8], rbp
0x18000767a  lea     rcx, [rsp+0A8h+SystemTime]; lpSystemTime
0x18000767f  mov     [rsp+0A8h+arg_10], rsi
0x180007687  xorps   xmm0, xmm0
0x18000768a  mov     [rsp+0A8h+var_10], rdi
0x180007692  mov     [rsp+0A8h+var_18], r12
0x18000769a  mov     [rsp+0A8h+var_20], r14
0x1800076a2  mov     [rsp+0A8h+var_28], r15
0x1800076aa  movups  xmmword ptr [rsp+0A8h+SystemTime.wYear], xmm0
0x1800076af  call    cs:__imp_GetLocalTime
0x1800076b5  mov     edi, [rbx+58h]
0x1800076b8  xor     eax, eax
0x1800076ba  mov     [rsp+0A8h+var_48], ax
0x1800076bf  test    dil, 4
0x1800076c3  jz      short loc_1800076F1
0x1800076c5  mov     edx, 41302h
0x1800076ca  mov     ecx, edi
0x1800076cc  btr     ecx, 12h
0x1800076d0  test    ax, ax
0x1800076d3  jnz     loc_1800077DF
0x1800076d9  cmp     edx, 41308h
0x1800076df  jz      loc_1800077DF
0x1800076e5  bts     ecx, 16h
0x1800076e9  mov     [rbx+58h], ecx
0x1800076ec  jmp     loc_180007803
0x1800076f1  movzx   r15d, word ptr [rbx+20h]
0x1800076f6  and     edi, 7FFFh
0x1800076fc  xor     ebp, ebp
0x1800076fe  xor     r14d, r14d
0x180007701  xor     esi, esi
0x180007703  mov     r12d, 1
0x180007709  cmp     si, r15w
0x18000770d  jnb     loc_18000779A
0x180007713  movzx   eax, si
0x180007716  lea     r9, [rsp+0A8h+var_48]; unsigned __int16 *
0x18000771b  xor     r8d, r8d; struct _SYSTEMTIME *
0x18000771e  lea     rdx, [rsp+0A8h+SystemTime]; struct _SYSTEMTIME *
0x180007723  lea     rcx, [rax+rax*2]
0x180007727  movzx   eax, word ptr [rbx+46h]
0x18000772b  mov     [rsp+0A8h+var_58], ax; unsigned __int16
0x180007730  movzx   eax, word ptr [rbx+44h]
0x180007734  mov     [rsp+0A8h+var_60], ax; unsigned __int16
0x180007739  mov     eax, [rbx+4Ch]
0x18000773c  mov     [rsp+0A8h+var_68], eax; unsigned int
0x180007740  mov     [rsp+0A8h+var_70], edi; unsigned int
0x180007744  shl     rcx, 4
0x180007748  add     rcx, [rbx+18h]; struct _TASK_TRIGGER *
0x18000774c  mov     [rsp+0A8h+var_78], 0; unsigned __int16 *
0x180007755  mov     [rsp+0A8h+var_80], 0; struct CTimeRunList *
0x18000775e  mov     [rsp+0A8h+var_88], r12w; unsigned __int16
0x180007764  call    ?GetTriggerRunTimes@@YAJAEAU_TASK_TRIGGER@@PEBU_SYSTEMTIME@@1PEAGGPEAVCTimeRunList@@2KKGG@Z; GetTriggerRunTimes(_TASK_TRIGGER &,_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *,ulong,ulong,ushort,ushort)
0x180007769  mov     ecx, eax
0x18000776b  test    eax, eax
0x18000776d  js      loc_180007811
0x180007773  movzx   eax, [rsp+0A8h+var_48]
0x180007778  cmp     ecx, 41308h
0x18000777e  jnz     short loc_180007785
0x180007780  mov     ebp, r12d
0x180007783  jmp     short loc_180007792
0x180007785  test    ecx, ecx
0x180007787  jnz     short loc_180007792
0x180007789  mov     r14d, r12d
0x18000778c  cmp     ax, r12w
0x180007790  jnb     short loc_18000779F
0x180007792  inc     si
0x180007795  jmp     loc_180007709
0x18000779a  test    r14d, r14d
0x18000779d  jz      short loc_1800077B3
0x18000779f  test    ax, ax
0x1800077a2  jnz     short loc_1800077AF
0x1800077a4  test    ebp, ebp
0x1800077a6  jz      short loc_1800077AF
0x1800077a8  mov     edx, 41308h
0x1800077ad  jmp     short loc_1800077C0
0x1800077af  xor     edx, edx
0x1800077b1  jmp     short loc_1800077C0
0x1800077b3  xor     edx, edx
0x1800077b5  test    ebp, ebp
0x1800077b7  setnz   dl
0x1800077ba  add     edx, 41307h
0x1800077c0  mov     ecx, [rbx+58h]
0x1800077c3  cmp     edx, 41307h
0x1800077c9  jnz     loc_1800076CC
0x1800077cf  bts     ecx, 12h
0x1800077d3  mov     dword ptr [rbx+54h], 41305h
0x1800077da  mov     [rbx+58h], ecx
0x1800077dd  jmp     short loc_180007803
0x1800077df  btr     ecx, 16h
0x1800077e3  mov     [rbx+58h], ecx
0x1800077e6  bt      ecx, 18h
0x1800077ea  jnb     short loc_180007803
0x1800077ec  cmp     word ptr [rbx+60h], 0
0x1800077f1  jnz     short loc_1800077FC
0x1800077f3  mov     dword ptr [rbx+54h], 41303h
0x1800077fa  jmp     short loc_180007803
0x1800077fc  mov     dword ptr [rbx+54h], 41300h
0x180007803  test    cl, 4
0x180007806  jz      short loc_18000780F
0x180007808  mov     dword ptr [rbx+54h], 41302h
0x18000780f  xor     eax, eax
0x180007811  mov     r14, [rsp+0A8h+var_20]
0x180007819  mov     r12, [rsp+0A8h+var_18]
0x180007821  mov     rdi, [rsp+0A8h+var_10]
0x180007829  mov     rsi, [rsp+0A8h+arg_10]
0x180007831  mov     rbp, [rsp+0A8h+arg_8]
0x180007839  mov     r15, [rsp+0A8h+var_28]
0x180007841  mov     rcx, [rsp+0A8h+var_30]
0x180007846  xor     rcx, rsp; StackCookie
0x180007849  call    __security_check_cookie
0x18000784e  add     rsp, 0A0h
0x180007855  pop     rbx
0x180007856  retn
```
