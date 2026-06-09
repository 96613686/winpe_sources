# CreateIniTxSFilters

- ea: `0x1800096d8`
- end: `0x18000985a`
- name: `CreateIniTxSFilters`
- size: `386`
- prototype: `__int64 __fastcall(__int64, int, int, int, LPVOID *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18001e12c`
- `0x18001e9f0`

## callees

- `0x1800096d8`
- `0x180009860`
- `0x18000c9fc`
- `0x18000e510`
- `0x18001d48c`
- `0x18001df38`
- `0x18001e21c`
- `0x18002088c`

## pseudocode

```c
__int64 __fastcall CreateIniTxSFilters(__int64 a1, int a2, int a3, int a4, LPVOID *a5)
{
  void *v5; // rdi
  unsigned int IniMirroredTxFilter; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  void *v14; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-18h] BYREF
  __int64 v16; // [rsp+40h] [rbp-10h] BYREF

  v5 = 0;
  lpMem = 0;
  v14 = 0;
  v16 = 0;
  if ( !a3 )
  {
    IniMirroredTxFilter = 0;
LABEL_21:
    *a5 = 0;
    goto LABEL_24;
  }
  IniMirroredTxFilter = ApplyTxTransform(a1, a2, a3, a4, (__int64)&lpMem);
  if ( IniMirroredTxFilter )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v12 = 46;
LABEL_18:
      WPP_SF_d(v11[2], v12, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids, IniMirroredTxFilter);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  if ( *(_DWORD *)(a1 + 36) )
  {
    IniMirroredTxFilter = CreateIniMirroredTxFilter(a1, (__int64 *)&v14);
    if ( IniMirroredTxFilter )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          WPP_d3e4a8f1960430b115941304a22a5749_Traceguids,
          IniMirroredTxFilter);
      v5 = v14;
      goto LABEL_19;
    }
    v5 = v14;
    if ( !(unsigned int)EqualIniTxFilterPKeys(a1, v14) )
    {
      IniMirroredTxFilter = ApplyTxTransform((_DWORD)v5, a2, a3, a4, (__int64)&v16);
      if ( IniMirroredTxFilter )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v12 = 48;
          goto LABEL_18;
        }
LABEL_19:
        if ( lpMem )
          FreeIniTxSFilterList(lpMem);
        goto LABEL_21;
      }
      AddToSpecificTxList((__int64 *)&lpMem, v16);
    }
  }
  *a5 = lpMem;
LABEL_24:
  if ( v5 )
    FreeIniTxFilter(v5);
  return IniMirroredTxFilter;
}

```

## disassembly

```asm
0x1800096d8  push    rbp
0x1800096da  push    rbx
0x1800096db  push    rsi
0x1800096dc  push    rdi
0x1800096dd  push    r12
0x1800096df  push    r14
0x1800096e1  push    r15
0x1800096e3  mov     rbp, rsp
0x1800096e6  sub     rsp, 50h
0x1800096ea  xor     edi, edi
0x1800096ec  mov     [rbp+lpMem], 0
0x1800096f4  mov     [rbp+var_20], rdi
0x1800096f8  mov     r15, r9
0x1800096fb  mov     [rbp+var_10], rdi
0x1800096ff  mov     r14d, r8d
0x180009702  mov     r12, rdx
0x180009705  mov     rsi, rcx
0x180009708  test    r8d, r8d
0x18000970b  jnz     short loc_180009714
0x18000970d  xor     ebx, ebx
0x18000970f  jmp     loc_180009817
0x180009714  lea     rax, [rbp+lpMem]
0x180009718  mov     [rsp+50h+var_30], rax
0x18000971d  call    ApplyTxTransform
0x180009722  mov     ebx, eax
0x180009724  test    eax, eax
0x180009726  jz      short loc_180009753
0x180009728  mov     rcx, cs:WPP_GLOBAL_Control
0x18000972f  lea     rax, WPP_GLOBAL_Control
0x180009736  cmp     rcx, rax
0x180009739  jz      loc_180009809
0x18000973f  test    byte ptr [rcx+1Ch], 10h
0x180009743  jz      loc_180009809
0x180009749  mov     edx, 2Eh ; '.'
0x18000974e  jmp     loc_1800097F6
0x180009753  cmp     [rsi+24h], edi
0x180009756  jz      loc_180009831
0x18000975c  lea     rdx, [rbp+var_20]
0x180009760  mov     rcx, rsi
0x180009763  call    CreateIniMirroredTxFilter
0x180009768  mov     ebx, eax
0x18000976a  test    eax, eax
0x18000976c  jz      short loc_1800097A5
0x18000976e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009775  lea     rax, WPP_GLOBAL_Control
0x18000977c  cmp     rcx, rax
0x18000977f  jz      short loc_18000979F
0x180009781  test    byte ptr [rcx+1Ch], 10h
0x180009785  jz      short loc_18000979F
0x180009787  mov     rcx, [rcx+10h]
0x18000978b  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x180009792  mov     edx, 2Fh ; '/'
0x180009797  mov     r9d, ebx
0x18000979a  call    WPP_SF_d
0x18000979f  mov     rdi, [rbp+var_20]
0x1800097a3  jmp     short loc_180009809
0x1800097a5  mov     rdi, [rbp+var_20]
0x1800097a9  mov     rcx, rsi
0x1800097ac  mov     rdx, rdi
0x1800097af  call    EqualIniTxFilterPKeys
0x1800097b4  test    eax, eax
0x1800097b6  jnz     short loc_180009831
0x1800097b8  lea     rax, [rbp+var_10]
0x1800097bc  mov     r9, r15
0x1800097bf  mov     r8d, r14d
0x1800097c2  mov     [rsp+50h+var_30], rax
0x1800097c7  mov     rdx, r12
0x1800097ca  mov     rcx, rdi
0x1800097cd  call    ApplyTxTransform
0x1800097d2  mov     ebx, eax
0x1800097d4  test    eax, eax
0x1800097d6  jz      short loc_180009824
0x1800097d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097df  lea     rax, WPP_GLOBAL_Control
0x1800097e6  cmp     rcx, rax
0x1800097e9  jz      short loc_180009809
0x1800097eb  test    byte ptr [rcx+1Ch], 10h
0x1800097ef  jz      short loc_180009809
0x1800097f1  mov     edx, 30h ; '0'
0x1800097f6  mov     rcx, [rcx+10h]
0x1800097fa  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x180009801  mov     r9d, ebx
0x180009804  call    WPP_SF_d
0x180009809  mov     rcx, [rbp+lpMem]; lpMem
0x18000980d  test    rcx, rcx
0x180009810  jz      short loc_180009817
0x180009812  call    FreeIniTxSFilterList
0x180009817  mov     rax, [rbp+arg_20]
0x18000981b  mov     qword ptr [rax], 0
0x180009822  jmp     short loc_18000983C
0x180009824  mov     rdx, [rbp+var_10]
0x180009828  lea     rcx, [rbp+lpMem]
0x18000982c  call    AddToSpecificTxList
0x180009831  mov     rdx, [rbp+arg_20]
0x180009835  mov     rax, [rbp+lpMem]
0x180009839  mov     [rdx], rax
0x18000983c  test    rdi, rdi
0x18000983f  jz      short loc_180009849
0x180009841  mov     rcx, rdi; lpMem
0x180009844  call    FreeIniTxFilter
0x180009849  mov     eax, ebx
0x18000984b  add     rsp, 50h
0x18000984f  pop     r15
0x180009851  pop     r14
0x180009853  pop     r12
0x180009855  pop     rdi
0x180009856  pop     rsi
0x180009857  pop     rbx
0x180009858  pop     rbp
0x180009859  retn
```
