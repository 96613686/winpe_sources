# ExtSTASetWEPKeyMapping(EXTSTA_VELAN *,_DOT11_KM_WEP_KEY_MAPPING *,ulong)

- ea: `0x14006d810`
- end: `0x14006da84`
- name: `?ExtSTASetWEPKeyMapping@@YAJPEAUEXTSTA_VELAN@@PEAU_DOT11_KM_WEP_KEY_MAPPING@@K@Z`
- size: `628`
- prototype: `int(struct EXTSTA_VELAN *, struct _DOT11_KM_WEP_KEY_MAPPING *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x14000d22c`
- `0x140019bbc`
- `0x14006d810`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006d928`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006d928`
- `ntoskrnl!ExAllocatePool2` at `0x14006d93d`
- `ntoskrnl!ExAllocatePool2` at `0x14006d93d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006da33`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006da33`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006da44`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006da44`

## pseudocode

```c
__int64 __fastcall ExtSTASetWEPKeyMapping(
        struct EXTSTA_VELAN *a1,
        struct _DOT11_KM_WEP_KEY_MAPPING *a2,
        unsigned int a3)
{
  size_t v4; // r13
  unsigned int v6; // r10d
  _DOT11_BSS_TYPE DesiredBSSType; // ecx
  _DWORD *v8; // rdi
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // rdx
  unsigned int v12; // r11d
  __int64 v13; // r8
  __int64 v14; // rdx
  unsigned int v15; // r15d
  unsigned int v16; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  _DWORD *v19; // rsi
  size_t v20; // r8
  unsigned int v21; // ebx

  v4 = a3;
  if ( *(_DWORD *)a2 != 1 )
    goto LABEL_41;
  v6 = *((_DWORD *)a2 + 9);
  if ( a3 - 40 < v6 )
  {
    v21 = -1073741789;
    goto LABEL_42;
  }
  if ( v6 > 0xFFFF )
  {
LABEL_41:
    v21 = -1073741811;
    goto LABEL_42;
  }
  DesiredBSSType = a1->Rw.DesiredBSSType;
  v8 = (_DWORD *)((char *)a2 + 20);
  v9 = *((unsigned int *)a2 + 5);
  if ( a2 != (struct _DOT11_KM_WEP_KEY_MAPPING *)-20LL )
    *v8 = v9;
  v10 = 1960;
  v11 = 0;
  if ( DesiredBSSType != dot11_BSS_type_infrastructure )
    v10 = 2072;
  v12 = *(unsigned int *)((char *)&a1->ModuleStatus.uValue + v10);
  v13 = 1968;
  if ( DesiredBSSType != dot11_BSS_type_infrastructure )
    v13 = 2080;
  while ( 1 )
  {
    if ( (unsigned int)v11 >= v12 )
    {
      if ( (((_DWORD)v9 - 1) & 0xFFFFFFFB) == 0 )
      {
        v14 = 0;
        v9 = 257;
        while ( (unsigned int)v14 < v12 )
        {
          if ( *(_DWORD *)(*(_QWORD *)((char *)&a1->ModuleStatus.0 + v13) + 4 * v14) == 257 )
          {
            if ( v8 )
              *v8 = 257;
            goto LABEL_20;
          }
          v14 = (unsigned int)(v14 + 1);
        }
      }
      goto LABEL_41;
    }
    if ( *(_DWORD *)(*(_QWORD *)((char *)&a1->ModuleStatus.0 + v13) + 4 * v11) == (_DWORD)v9 )
      break;
    v11 = (unsigned int)(v11 + 1);
  }
LABEL_20:
  v15 = v6 + 32;
  v16 = v6 + 48;
  if ( v6 + 48 < 0x10 )
    goto LABEL_39;
  if ( v16 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    goto LABEL_29;
  }
  if ( v16 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_29;
  }
  if ( v16 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_29;
  }
  if ( v16 > 0x800 )
  {
    p_DeviceQueue = 0;
    Pool2 = (_DWORD *)ExAllocatePool2(64, v16, 808464432, v9);
  }
  else
  {
    p_DeviceQueue = &stru_1400B0180;
LABEL_29:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
  }
  if ( !Pool2 )
  {
LABEL_39:
    v21 = -1073741670;
    goto LABEL_42;
  }
  Pool2[2] = 808464432;
  v19 = Pool2 + 4;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  memset(Pool2 + 4, 0, v15);
  *v19 = 1048960;
  v19[1] = v15 - 12;
  v19[2] = v15 - 12;
  v19[3] = *((_DWORD *)a2 + 3);
  *((_WORD *)v19 + 8) = *((_WORD *)a2 + 8);
  *((_BYTE *)v19 + 28) = *((_DWORD *)a2 + 8) != 1;
  v19[5] = *v8;
  v19[6] = *((_DWORD *)a2 + 6);
  *((_BYTE *)v19 + 29) = *((_DWORD *)a2 + 7) != 0;
  v20 = *((unsigned __int16 *)a2 + 18);
  *((_WORD *)v19 + 15) = *((_WORD *)a2 + 18);
  memmove(v19 + 8, (char *)a2 + 40, v20);
  v21 = PtRequestAdapterSync(a1->pGenVElan->pAdapt, 1u, 0xE01018Cu, v19, v15);
  if ( v21 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids);
  if ( v19 )
  {
    memset(v19, 0, v15);
    if ( *((_QWORD *)v19 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v19 - 2), v19 - 4);
    else
      ExFreePoolWithTag(v19 - 4, *(v19 - 2));
  }
LABEL_42:
  memset(a2, 0, v4);
  return v21;
}

```

## disassembly

```asm
0x14006d810  push    rbx
0x14006d812  push    rbp
0x14006d813  push    rsi
0x14006d814  push    rdi
0x14006d815  push    r13
0x14006d817  push    r14
0x14006d819  push    r15
0x14006d81b  sub     rsp, 30h
0x14006d81f  cmp     dword ptr [rdx], 1
0x14006d822  mov     rbp, rdx
0x14006d825  mov     r13d, r8d
0x14006d828  mov     r14, rcx
0x14006d82b  jnz     loc_14006DA60
0x14006d831  mov     r10d, [rdx+24h]
0x14006d835  lea     eax, [r13-28h]
0x14006d839  cmp     eax, r10d
0x14006d83c  jb      loc_14006DA59
0x14006d842  cmp     r10d, 0FFFFh
0x14006d849  ja      loc_14006DA60
0x14006d84f  mov     ecx, [rcx+6BCh]
0x14006d855  lea     rdi, [rdx+14h]
0x14006d859  mov     r9d, [rdi]
0x14006d85c  test    rdi, rdi
0x14006d85f  jz      short loc_14006D864
0x14006d861  mov     [rdi], r9d
0x14006d864  mov     eax, 7A8h
0x14006d869  xor     edx, edx
0x14006d86b  cmp     ecx, 1
0x14006d86e  lea     r8d, [rax+70h]
0x14006d872  cmovnz  eax, r8d
0x14006d876  mov     r11d, [rax+r14]
0x14006d87a  lea     eax, [r8+8]
0x14006d87e  lea     r8d, [rax-70h]
0x14006d882  cmovnz  r8d, eax
0x14006d886  cmp     edx, r11d
0x14006d889  jnb     short loc_14006D899
0x14006d88b  mov     rax, [r8+r14]
0x14006d88f  cmp     [rax+rdx*4], r9d
0x14006d893  jz      short loc_14006D8CF
0x14006d895  inc     edx
0x14006d897  jmp     short loc_14006D886
0x14006d899  lea     eax, [r9-1]
0x14006d89d  test    eax, 0FFFFFFFBh
0x14006d8a2  jnz     loc_14006DA60
0x14006d8a8  xor     edx, edx
0x14006d8aa  mov     r9d, 101h
0x14006d8b0  cmp     edx, r11d
0x14006d8b3  jnb     loc_14006DA60
0x14006d8b9  mov     rax, [r8+r14]
0x14006d8bd  cmp     [rax+rdx*4], r9d
0x14006d8c1  jz      short loc_14006D8C7
0x14006d8c3  inc     edx
0x14006d8c5  jmp     short loc_14006D8B0
0x14006d8c7  test    rdi, rdi
0x14006d8ca  jz      short loc_14006D8CF
0x14006d8cc  mov     [rdi], r9d
0x14006d8cf  lea     r15d, [r10+20h]
0x14006d8d3  lea     eax, [r15+10h]
0x14006d8d7  cmp     eax, 10h
0x14006d8da  jb      loc_14006DA52
0x14006d8e0  mov     ecx, 40h ; '@'
0x14006d8e5  mov     esi, 30303030h
0x14006d8ea  cmp     eax, ecx
0x14006d8ec  ja      short loc_14006D8F7
0x14006d8ee  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14006d8f5  jmp     short loc_14006D925
0x14006d8f7  cmp     eax, 100h
0x14006d8fc  ja      short loc_14006D907
0x14006d8fe  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006d905  jmp     short loc_14006D925
0x14006d907  cmp     eax, 400h
0x14006d90c  ja      short loc_14006D917
0x14006d90e  lea     rbx, Lookaside
0x14006d915  jmp     short loc_14006D925
0x14006d917  cmp     eax, 800h
0x14006d91c  ja      short loc_14006D936
0x14006d91e  lea     rbx, stru_1400B0180
0x14006d925  mov     rcx, rbx; Lookaside
0x14006d928  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006d92f  nop     dword ptr [rax+rax+00h]
0x14006d934  jmp     short loc_14006D949
0x14006d936  xor     ebx, ebx
0x14006d938  mov     edx, eax
0x14006d93a  mov     r8d, esi
0x14006d93d  call    cs:__imp_ExAllocatePool2
0x14006d944  nop     dword ptr [rax+rax+00h]
0x14006d949  test    rax, rax
0x14006d94c  jz      loc_14006DA52
0x14006d952  mov     [rax+8], esi
0x14006d955  xor     edx, edx; Val
0x14006d957  lea     rsi, [rax+10h]
0x14006d95b  mov     r8d, r15d; Size
0x14006d95e  mov     rcx, rsi; void *
0x14006d961  mov     [rax], rbx
0x14006d964  call    memset
0x14006d969  mov     dword ptr [rsi], 100180h
0x14006d96f  lea     eax, [r15-0Ch]
0x14006d973  mov     [rsi+4], eax
0x14006d976  lea     rdx, [rbp+28h]; Src
0x14006d97a  mov     [rsi+8], eax
0x14006d97d  lea     rcx, [rsi+20h]; void *
0x14006d981  mov     eax, [rbp+0Ch]
0x14006d984  mov     [rsi+0Ch], eax
0x14006d987  movzx   eax, word ptr [rbp+10h]
0x14006d98b  mov     [rsi+10h], ax
0x14006d98f  cmp     dword ptr [rbp+20h], 1
0x14006d993  setnz   al
0x14006d996  mov     [rsi+1Ch], al
0x14006d999  mov     eax, [rdi]
0x14006d99b  mov     [rsi+14h], eax
0x14006d99e  mov     eax, [rbp+18h]
0x14006d9a1  mov     [rsi+18h], eax
0x14006d9a4  cmp     dword ptr [rbp+1Ch], 0
0x14006d9a8  setnz   al
0x14006d9ab  mov     [rsi+1Dh], al
0x14006d9ae  movzx   eax, word ptr [rbp+24h]
0x14006d9b2  mov     r8d, eax; Size
0x14006d9b5  mov     [rsi+1Eh], ax
0x14006d9b9  call    memmove
0x14006d9be  mov     rcx, [r14+0A38h]
0x14006d9c5  mov     r9, rsi; void *
0x14006d9c8  mov     edx, 1; unsigned int
0x14006d9cd  mov     [rsp+68h+var_48], r15d; unsigned int
0x14006d9d2  mov     r8d, 0E01018Ch; unsigned int
0x14006d9d8  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006d9dc  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006d9e1  mov     ebx, eax
0x14006d9e3  test    eax, eax
0x14006d9e5  jz      short loc_14006DA0F
0x14006d9e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d9ee  lea     rax, WPP_GLOBAL_Control
0x14006d9f5  cmp     rcx, rax
0x14006d9f8  jz      short loc_14006DA0F
0x14006d9fa  mov     rcx, [rcx+18h]
0x14006d9fe  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006da05  mov     edx, 1Bh
0x14006da0a  call    WPP_SF_
0x14006da0f  test    rsi, rsi
0x14006da12  jz      short loc_14006DA65
0x14006da14  mov     r8d, r15d; Size
0x14006da17  xor     edx, edx; Val
0x14006da19  mov     rcx, rsi; void *
0x14006da1c  call    memset
0x14006da21  lea     rcx, [rsi-10h]; P
0x14006da25  mov     rax, [rcx]
0x14006da28  test    rax, rax
0x14006da2b  jz      short loc_14006DA41
0x14006da2d  mov     rdx, rcx; Entry
0x14006da30  mov     rcx, rax; Lookaside
0x14006da33  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006da3a  nop     dword ptr [rax+rax+00h]
0x14006da3f  jmp     short loc_14006DA65
0x14006da41  mov     edx, [rcx+8]; Tag
0x14006da44  call    cs:__imp_ExFreePoolWithTag
0x14006da4b  nop     dword ptr [rax+rax+00h]
0x14006da50  jmp     short loc_14006DA65
0x14006da52  mov     ebx, 0C000009Ah
0x14006da57  jmp     short loc_14006DA65
0x14006da59  mov     ebx, 0C0000023h
0x14006da5e  jmp     short loc_14006DA65
0x14006da60  mov     ebx, 0C000000Dh
0x14006da65  mov     r8, r13; Size
0x14006da68  xor     edx, edx; Val
0x14006da6a  mov     rcx, rbp; void *
0x14006da6d  call    memset
0x14006da72  mov     eax, ebx
0x14006da74  add     rsp, 30h
0x14006da78  pop     r15
0x14006da7a  pop     r14
0x14006da7c  pop     r13
0x14006da7e  pop     rdi
0x14006da7f  pop     rsi
0x14006da80  pop     rbp
0x14006da81  pop     rbx
0x14006da82  retn
```
