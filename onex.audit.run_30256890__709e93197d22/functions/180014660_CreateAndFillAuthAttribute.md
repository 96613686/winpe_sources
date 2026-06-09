# CreateAndFillAuthAttribute

- ea: `0x180014660`
- end: `0x18001486a`
- name: `CreateAndFillAuthAttribute`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014190`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180014660`
- `0x1800214f0`
- `0x180021b6c`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x1800146d7`
- `MobileNetworking!AllocateMemory` at `0x18001472d`
- `MobileNetworking!AllocateMemory` at `0x1800147a6`
- `MobileNetworking!AllocateMemory` at `0x1800146d7`
- `MobileNetworking!AllocateMemory` at `0x18001472d`
- `MobileNetworking!AllocateMemory` at `0x1800147a6`

## string_xrefs

- `0x1800146c3`: `CreateAndFillAuthAttribute`
- `0x18001470c`: `CreateAndFillAuthAttribute`
- `0x180014790`: `CreateAndFillAuthAttribute`

## pseudocode

```c
__int64 __fastcall CreateAndFillAuthAttribute(unsigned int a1, _QWORD *a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  unsigned int Memory; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 v13; // rdx
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v15 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids);
  *a2 = 0;
  Memory = AllocateMemory(16, &v15, "CreateAndFillAuthAttribute", 480);
  v9 = Memory;
  if ( !Memory )
  {
    *(_DWORD *)v15 = 1;
    Memory = AllocateMemory(16, v15 + 8, "CreateAndFillAuthAttribute", 488);
    v9 = Memory;
    if ( Memory )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_18;
      v11 = 29;
      goto LABEL_17;
    }
    v12 = a6;
    *(_DWORD *)(*(_QWORD *)(v15 + 8) + 4LL) = 6;
    **(_DWORD **)(v15 + 8) = 8102;
    if ( v12 )
    {
      Memory = AllocateMemory(7, *(_QWORD *)(v15 + 8) + 8LL, "CreateAndFillAuthAttribute", 527);
      v9 = Memory;
      if ( Memory )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_18;
        v11 = 31;
        goto LABEL_17;
      }
      v13 = *(_QWORD *)(*(_QWORD *)(v15 + 8) + 8LL);
      *(_DWORD *)v13 = *(_DWORD *)v12;
      *(_WORD *)(v13 + 4) = *(_WORD *)(v12 + 4);
    }
    else
    {
      *(_QWORD *)(*(_QWORD *)(v15 + 8) + 8LL) = 0;
    }
    *a2 = v15;
    goto LABEL_22;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
    goto LABEL_18;
  v11 = 28;
LABEL_17:
  WPP_SF_dd(v10[7], v11, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, a1, Memory);
LABEL_18:
  DestroyAuthAttribute(v15);
  v15 = 0;
LABEL_22:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 33, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180014660  push    rbx
0x180014662  sub     rsp, 40h
0x180014666  mov     [rsp+48h+arg_0], rbp
0x18001466b  mov     ebp, ecx
0x18001466d  mov     [rsp+48h+arg_10], rsi
0x180014672  mov     rsi, rdx
0x180014675  mov     [rsp+48h+var_10], r14
0x18001467a  mov     [rsp+48h+var_18], r15
0x18001467f  xor     r15d, r15d
0x180014682  mov     [rsp+48h+arg_8], r15
0x180014687  mov     rcx, cs:WPP_GLOBAL_Control
0x18001468e  lea     r14, WPP_GLOBAL_Control
0x180014695  cmp     rcx, r14
0x180014698  jz      short loc_1800146B8
0x18001469a  test    dword ptr [rcx+44h], 800h
0x1800146a1  jz      short loc_1800146B8
0x1800146a3  mov     rcx, [rcx+38h]
0x1800146a7  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x1800146ae  mov     edx, 1Bh
0x1800146b3  call    WPP_SF_
0x1800146b8  mov     r9d, 1E0h
0x1800146be  mov     [rsp+48h+arg_18], rdi
0x1800146c3  lea     r8, aCreateandfilla; "CreateAndFillAuthAttribute"
0x1800146ca  mov     [rsi], r15
0x1800146cd  lea     rdx, [rsp+48h+arg_8]
0x1800146d2  mov     ecx, 10h
0x1800146d7  call    cs:__imp_AllocateMemory
0x1800146dd  mov     ebx, eax
0x1800146df  test    eax, eax
0x1800146e1  jz      short loc_180014707
0x1800146e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146ea  cmp     rcx, r14
0x1800146ed  jz      loc_1800147E0
0x1800146f3  test    byte ptr [rcx+44h], 1
0x1800146f7  jz      loc_1800147E0
0x1800146fd  mov     edx, 1Ch
0x180014702  jmp     loc_1800147C9
0x180014707  mov     rax, [rsp+48h+arg_8]
0x18001470c  lea     r8, aCreateandfilla; "CreateAndFillAuthAttribute"
0x180014713  mov     r9d, 1E8h
0x180014719  mov     ecx, 10h
0x18001471e  mov     dword ptr [rax], 1
0x180014724  mov     rdx, [rsp+48h+arg_8]
0x180014729  add     rdx, 8
0x18001472d  call    cs:__imp_AllocateMemory
0x180014733  mov     ebx, eax
0x180014735  test    eax, eax
0x180014737  jz      short loc_18001475A
0x180014739  mov     rcx, cs:WPP_GLOBAL_Control
0x180014740  cmp     rcx, r14
0x180014743  jz      loc_1800147E0
0x180014749  test    byte ptr [rcx+44h], 1
0x18001474d  jz      loc_1800147E0
0x180014753  mov     edx, 1Dh
0x180014758  jmp     short loc_1800147C9
0x18001475a  mov     rax, [rsp+48h+arg_8]
0x18001475f  mov     rdi, [rsp+48h+arg_28]
0x180014764  mov     rcx, [rax+8]
0x180014768  mov     dword ptr [rcx+4], 6
0x18001476f  mov     rax, [rsp+48h+arg_8]
0x180014774  mov     rcx, [rax+8]
0x180014778  mov     dword ptr [rcx], 1FA6h
0x18001477e  mov     rax, [rsp+48h+arg_8]
0x180014783  test    rdi, rdi
0x180014786  jz      loc_18001480C
0x18001478c  mov     rdx, [rax+8]
0x180014790  lea     r8, aCreateandfilla; "CreateAndFillAuthAttribute"
0x180014797  add     rdx, 8
0x18001479b  mov     r9d, 20Fh
0x1800147a1  mov     ecx, 7
0x1800147a6  call    cs:__imp_AllocateMemory
0x1800147ac  mov     ebx, eax
0x1800147ae  test    eax, eax
0x1800147b0  jz      short loc_1800147F1
0x1800147b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147b9  cmp     rcx, r14
0x1800147bc  jz      short loc_1800147E0
0x1800147be  test    byte ptr [rcx+44h], 1
0x1800147c2  jz      short loc_1800147E0
0x1800147c4  mov     edx, 1Fh
0x1800147c9  mov     rcx, [rcx+38h]
0x1800147cd  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x1800147d4  mov     r9d, ebp
0x1800147d7  mov     [rsp+48h+var_28], eax
0x1800147db  call    WPP_SF_dd
0x1800147e0  mov     rcx, [rsp+48h+arg_8]
0x1800147e5  call    DestroyAuthAttribute
0x1800147ea  mov     [rsp+48h+arg_8], r15
0x1800147ef  jmp     short loc_18001481C
0x1800147f1  mov     rax, [rsp+48h+arg_8]
0x1800147f6  mov     rcx, [rax+8]
0x1800147fa  mov     eax, [rdi]
0x1800147fc  mov     rdx, [rcx+8]
0x180014800  mov     [rdx], eax
0x180014802  movzx   eax, word ptr [rdi+4]
0x180014806  mov     [rdx+4], ax
0x18001480a  jmp     short loc_180014814
0x18001480c  mov     rcx, [rax+8]
0x180014810  mov     [rcx+8], r15
0x180014814  mov     rax, [rsp+48h+arg_8]
0x180014819  mov     [rsi], rax
0x18001481c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014823  mov     r15, [rsp+48h+var_18]
0x180014828  cmp     rcx, r14
0x18001482b  mov     r14, [rsp+48h+var_10]
0x180014830  mov     rdi, [rsp+48h+arg_18]
0x180014835  mov     rsi, [rsp+48h+arg_10]
0x18001483a  mov     rbp, [rsp+48h+arg_0]
0x18001483f  jz      short loc_180014862
0x180014841  test    dword ptr [rcx+44h], 800h
0x180014848  jz      short loc_180014862
0x18001484a  mov     rcx, [rcx+38h]
0x18001484e  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x180014855  mov     edx, 21h ; '!'
0x18001485a  mov     r9d, ebx
0x18001485d  call    WPP_SF_D
0x180014862  mov     eax, ebx
0x180014864  add     rsp, 40h
0x180014868  pop     rbx
0x180014869  retn
```
