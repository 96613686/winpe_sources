# PmGetProfileXml(_GUID *,ushort const *,ulong,ushort * *)

- ea: `0x18000ca8c`
- end: `0x18000cbb8`
- name: `?PmGetProfileXml@@YAKPEAU_GUID@@PEBGKPEAPEAG@Z`
- size: `300`
- prototype: `__int64 __fastcall(struct _GUID *, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001fb6c`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18000ca8c`
- `0x18000d784`
- `0x18000d898`
- `0x18000e43c`
- `0x180032f7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cae7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cae7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cb76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cb76`

## pseudocode

```c
__int64 __fastcall PmGetProfileXml(
        struct _GUID *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 **a4)
{
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // rax
  unsigned int ProfileXml; // eax
  struct _PM_PCB *v11; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+28h] [rbp-40h] BYREF
  unsigned int v13; // [rsp+30h] [rbp-38h]
  int v14; // [rsp+34h] [rbp-34h]
  struct _PM_PCB_LIST *v15; // [rsp+78h] [rbp+10h] BYREF

  v15 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 63, WPP_935883eb83d333df730e157613565e66_Traceguids);
  }
  EnterCriticalSection(&stru_180052D40);
  v7 = PmpReferencePcbList(a1, a3, &v15);
  if ( !v7 )
  {
    v11 = 0;
    v14 = 0;
    v12 = 0;
    v13 = a3;
    v7 = PmpEnumPcbsPcbList(
           v15,
           (unsigned int (*)(struct _PM_PCB *, void *, struct _PM_PCB **))PmpFindKeyPcbCallback,
           &v12,
           &v11);
    if ( !v7 )
    {
      if ( v11 )
      {
        v8 = (const unsigned __int16 *)*((_QWORD *)v11 + 7);
        if ( v8 )
          ProfileXml = PmpDuplicateString(v8, a4);
        else
          ProfileXml = LpGenerateProfileXml(*((_QWORD *)v11 + 6), a4);
        v7 = ProfileXml;
      }
      else
      {
        v7 = 1168;
      }
    }
  }
  LeaveCriticalSection(&stru_180052D40);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 64, WPP_935883eb83d333df730e157613565e66_Traceguids, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x18000ca8c  mov     [rsp+arg_8], rdx
0x18000ca91  push    rbx
0x18000ca92  push    rsi
0x18000ca93  push    rdi
0x18000ca94  push    r14
0x18000ca96  sub     rsp, 48h
0x18000ca9a  mov     rdi, r9
0x18000ca9d  mov     [rsp+68h+arg_8], 0
0x18000caa6  mov     esi, r8d
0x18000caa9  mov     rbx, rcx
0x18000caac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cab3  lea     r14, WPP_GLOBAL_Control
0x18000caba  cmp     rcx, r14
0x18000cabd  jz      short loc_18000CAE0
0x18000cabf  cmp     byte ptr [rcx+19h], 4
0x18000cac3  jb      short loc_18000CAE0
0x18000cac5  test    byte ptr [rcx+1Ch], 1
0x18000cac9  jz      short loc_18000CAE0
0x18000cacb  mov     rcx, [rcx+10h]
0x18000cacf  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000cad6  mov     edx, 3Fh ; '?'
0x18000cadb  call    WPP_SF_
0x18000cae0  lea     rcx, stru_180052D40; lpCriticalSection
0x18000cae7  call    cs:__imp_EnterCriticalSection
0x18000caed  lea     r8, [rsp+68h+arg_8]; struct _PM_PCB_LIST **
0x18000caf2  mov     edx, esi; unsigned int
0x18000caf4  mov     rcx, rbx; struct _GUID *
0x18000caf7  call    ?PmpReferencePcbList@@YAKPEAU_GUID@@KPEAPEAU_PM_PCB_LIST@@@Z; PmpReferencePcbList(_GUID *,ulong,_PM_PCB_LIST * *)
0x18000cafc  mov     ebx, eax
0x18000cafe  test    eax, eax
0x18000cb00  jnz     short loc_18000CB6F
0x18000cb02  mov     rcx, [rsp+68h+arg_8]; struct _PM_PCB_LIST *
0x18000cb07  lea     r9, [rsp+68h+var_48]; struct _PM_PCB **
0x18000cb0c  lea     r8, [rsp+68h+var_40]; void *
0x18000cb11  mov     [rsp+68h+var_48], 0
0x18000cb1a  lea     rdx, ?PmpFindKeyPcbCallback@@YAKPEAU_PM_PCB@@PEAXPEAPEAU1@@Z; unsigned int (*)(struct _PM_PCB *, void *, struct _PM_PCB **)
0x18000cb21  mov     [rsp+68h+var_34], eax
0x18000cb25  mov     [rsp+68h+var_40], 0
0x18000cb2e  mov     [rsp+68h+var_38], esi
0x18000cb32  call    ?PmpEnumPcbsPcbList@@YAKPEAU_PM_PCB_LIST@@P6AKPEAU_PM_PCB@@PEAXPEAPEAU2@@Z23@Z; PmpEnumPcbsPcbList(_PM_PCB_LIST *,ulong (*)(_PM_PCB *,void *,_PM_PCB * *),void *,_PM_PCB * *)
0x18000cb37  mov     ebx, eax
0x18000cb39  test    eax, eax
0x18000cb3b  jnz     short loc_18000CB6F
0x18000cb3d  mov     rcx, [rsp+68h+var_48]
0x18000cb42  test    rcx, rcx
0x18000cb45  jz      short loc_18000CB6A
0x18000cb47  mov     rax, [rcx+38h]
0x18000cb4b  mov     rdx, rdi; unsigned __int16 **
0x18000cb4e  test    rax, rax
0x18000cb51  jz      short loc_18000CB5D
0x18000cb53  mov     rcx, rax; Src
0x18000cb56  call    ?PmpDuplicateString@@YAKPEBGPEAPEAG@Z; PmpDuplicateString(ushort const *,ushort * *)
0x18000cb5b  jmp     short loc_18000CB66
0x18000cb5d  mov     rcx, [rcx+30h]
0x18000cb61  call    LpGenerateProfileXml
0x18000cb66  mov     ebx, eax
0x18000cb68  jmp     short loc_18000CB6F
0x18000cb6a  mov     ebx, 490h
0x18000cb6f  lea     rcx, stru_180052D40; lpCriticalSection
0x18000cb76  call    cs:__imp_LeaveCriticalSection
0x18000cb7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb83  cmp     rcx, r14
0x18000cb86  jz      short loc_18000CBAC
0x18000cb88  cmp     byte ptr [rcx+19h], 4
0x18000cb8c  jb      short loc_18000CBAC
0x18000cb8e  test    byte ptr [rcx+1Ch], 1
0x18000cb92  jz      short loc_18000CBAC
0x18000cb94  mov     rcx, [rcx+10h]
0x18000cb98  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000cb9f  mov     edx, 40h ; '@'
0x18000cba4  mov     r9d, ebx
0x18000cba7  call    WPP_SF_d
0x18000cbac  mov     eax, ebx
0x18000cbae  add     rsp, 48h
0x18000cbb2  pop     r14
0x18000cbb4  pop     rdi
0x18000cbb5  pop     rsi
0x18000cbb6  pop     rbx
0x18000cbb7  retn
```
