# PmIsRedundantPath(_DEVICE_EXTENSION *,_DEVICE_EXTENSION *,uchar *)

- ea: `0x1400210a8`
- end: `0x1400212fa`
- name: `?PmIsRedundantPath@@YAJPEAU_DEVICE_EXTENSION@@0PEAE@Z`
- size: `594`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DEVICE_EXTENSION *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140020f90`
- `0x140023f38`

## callees

- `0x140010f20`
- `0x14001ff00`
- `0x140020240`
- `0x1400210a8`
- `0x14002133c`
- `0x1400217e8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400212a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400212a0`
- `ntoskrnl!ExAllocatePool2` at `0x140021179`
- `ntoskrnl!ExAllocatePool2` at `0x140021179`
- `ntoskrnl!RtlCompareMemory` at `0x140021285`
- `ntoskrnl!RtlCompareMemory` at `0x140021285`

## pseudocode

```c
__int64 __fastcall PmIsRedundantPath(struct _DEVICE_EXTENSION *a1, struct _DEVICE_EXTENSION *a2, unsigned __int8 *a3)
{
  int DriveGeometry; // ebx
  SIZE_T BytesPerSector; // rdi
  unsigned int v8; // eax
  _WORD *Pool2; // rsi
  struct _DEVICE_OBJECT *v10; // rcx
  __int16 v11; // bx
  __int16 v12; // ax
  struct _DEVICE_OBJECT *v13; // rcx
  int v14; // r8d
  union _LARGE_INTEGER v16; // [rsp+30h] [rbp-40h] BYREF
  void *Source2; // [rsp+38h] [rbp-38h]
  struct _GUID v18; // [rsp+40h] [rbp-30h] BYREF
  struct _DISK_GEOMETRY v19; // [rsp+50h] [rbp-20h] BYREF

  v19.BytesPerSector = 0;
  *(_WORD *)v18.Data4 = *(_WORD *)GUID_NULL.Data4;
  *(_WORD *)&v18.Data4[2] = *(_WORD *)&GUID_NULL.Data4[2];
  *(_WORD *)&v18.Data4[4] = *(_WORD *)&GUID_NULL.Data4[4];
  *a3 = 0;
  v16.QuadPart = 0;
  memset(&v19, 0, 20);
  *(_QWORD *)&v18.Data1 = 0;
  *(_WORD *)&v18.Data4[6] = *(_WORD *)&GUID_NULL.Data4[6];
  if ( *((_DWORD *)a1 + 12) )
  {
    DriveGeometry = 0;
LABEL_20:
    v14 = -2147221445;
    if ( !*a3 )
      v14 = -2147221446;
    PmLogError(a1, a2, v14);
    return (unsigned int)DriveGeometry;
  }
  DriveGeometry = PmGetDriveGeometry(*((struct _DEVICE_OBJECT **)a1 + 1), &v19);
  if ( DriveGeometry >= 0 )
  {
    BytesPerSector = v19.BytesPerSector;
    DriveGeometry = PmGetDriveGeometry(*((struct _DEVICE_OBJECT **)a2 + 1), &v19);
    if ( DriveGeometry >= 0 )
    {
      if ( v19.BytesPerSector != (_DWORD)BytesPerSector )
        goto LABEL_20;
      v8 = 3 * BytesPerSector;
      if ( (unsigned int)(3 * BytesPerSector) < 0x1000 )
        v8 = 4096;
      Pool2 = (_WORD *)ExAllocatePool2(66, v8, 1112108368);
      if ( !Pool2 )
        return (unsigned int)-1073741670;
      v10 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 1);
      v16.QuadPart = 0;
      DriveGeometry = PmSendIO(v10, 3u, Pool2, BytesPerSector, &v16);
      if ( DriveGeometry >= 0 )
      {
        DriveGeometry = PmSendIO(*((PDEVICE_OBJECT *)a2 + 1), 3u, (char *)Pool2 + BytesPerSector, BytesPerSector, &v16);
        if ( DriveGeometry >= 0 )
        {
          v11 = Pool2[222];
          do
          {
            PmUuidCreate(&v18);
            v12 = *(_WORD *)&v18.Data4[6]
                ^ *(_WORD *)&v18.Data4[4]
                ^ *(_WORD *)&v18.Data4[2]
                ^ *(_WORD *)v18.Data4
                ^ v18.Data3
                ^ v18.Data2
                ^ HIWORD(v18.Data1)
                ^ LOWORD(v18.Data1);
            Pool2[222] = v12;
          }
          while ( v12 == v11 );
          DriveGeometry = PmSendIO(*((PDEVICE_OBJECT *)a1 + 1), 4u, Pool2, BytesPerSector, &v16);
          if ( DriveGeometry >= 0 )
          {
            v13 = (struct _DEVICE_OBJECT *)*((_QWORD *)a2 + 1);
            Source2 = (char *)Pool2 + (unsigned int)(2 * BytesPerSector);
            DriveGeometry = PmSendIO(v13, 3u, Source2, BytesPerSector, &v16);
            if ( DriveGeometry >= 0
              && RtlCompareMemory((char *)Pool2 + BytesPerSector, Source2, BytesPerSector) != BytesPerSector )
            {
              *a3 = 1;
            }
          }
        }
      }
      ExFreePoolWithTag(Pool2, 0);
      if ( DriveGeometry >= 0 )
        goto LABEL_20;
    }
  }
  return (unsigned int)DriveGeometry;
}

```

## disassembly

```asm
0x1400210a8  mov     [rsp-38h+arg_18], rbx
0x1400210ad  push    rbp
0x1400210ae  push    rsi
0x1400210af  push    rdi
0x1400210b0  push    r12
0x1400210b2  push    r13
0x1400210b4  push    r14
0x1400210b6  push    r15
0x1400210b8  mov     rbp, rsp
0x1400210bb  sub     rsp, 70h
0x1400210bf  mov     rax, cs:__security_cookie
0x1400210c6  xor     rax, rsp
0x1400210c9  mov     [rbp-8], rax
0x1400210cd  xor     eax, eax
0x1400210cf  xor     esi, esi
0x1400210d1  mov     [rbp+var_20.BytesPerSector], eax
0x1400210d4  xorps   xmm0, xmm0
0x1400210d7  movzx   eax, word ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x1400210de  mov     r13, r8
0x1400210e1  mov     word ptr [rbp+var_30.Data4], ax
0x1400210e5  mov     r15, rdx
0x1400210e8  movzx   eax, word ptr cs:?GUID_NULL@@3U_GUID@@B.Data4+2; _GUID const GUID_NULL ...
0x1400210ef  mov     r14, rcx
0x1400210f2  mov     word ptr [rbp+var_30.Data4+2], ax
0x1400210f6  movzx   eax, word ptr cs:?GUID_NULL@@3U_GUID@@B.Data4+4; _GUID const GUID_NULL ...
0x1400210fd  mov     word ptr [rbp+var_30.Data4+4], ax
0x140021101  movzx   eax, word ptr cs:?GUID_NULL@@3U_GUID@@B.Data4+6; _GUID const GUID_NULL ...
0x140021108  mov     [r8], sil
0x14002110b  mov     qword ptr [rbp+var_40], rsi
0x14002110f  mov     dword ptr [rbp+var_20.Cylinders], esi
0x140021112  movups  xmmword ptr [rbp+var_20.Cylinders+4], xmm0
0x140021116  mov     qword ptr [rbp+var_30.Data1], rsi
0x14002111a  mov     word ptr [rbp+var_30.Data4+6], ax
0x14002111e  cmp     [rcx+30h], esi
0x140021121  ja      loc_1400212B4
0x140021127  mov     rcx, [rcx+8]; struct _DEVICE_OBJECT *
0x14002112b  lea     rdx, [rbp+var_20]; struct _DISK_GEOMETRY *
0x14002112f  call    ?PmGetDriveGeometry@@YAJPEAU_DEVICE_OBJECT@@PEAU_DISK_GEOMETRY@@@Z; PmGetDriveGeometry(_DEVICE_OBJECT *,_DISK_GEOMETRY *)
0x140021134  mov     ebx, eax
0x140021136  test    eax, eax
0x140021138  js      loc_1400212D3
0x14002113e  mov     rcx, [r15+8]; struct _DEVICE_OBJECT *
0x140021142  lea     rdx, [rbp+var_20]; struct _DISK_GEOMETRY *
0x140021146  mov     edi, [rbp+var_20.BytesPerSector]
0x140021149  call    ?PmGetDriveGeometry@@YAJPEAU_DEVICE_OBJECT@@PEAU_DISK_GEOMETRY@@@Z; PmGetDriveGeometry(_DEVICE_OBJECT *,_DISK_GEOMETRY *)
0x14002114e  mov     ebx, eax
0x140021150  test    eax, eax
0x140021152  js      loc_1400212D3
0x140021158  cmp     [rbp+var_20.BytesPerSector], edi
0x14002115b  jnz     loc_1400212B6
0x140021161  mov     ecx, 1000h
0x140021166  lea     eax, [rdi+rdi*2]
0x140021169  cmp     eax, ecx
0x14002116b  mov     r8d, 42496D50h
0x140021171  cmovb   eax, ecx
0x140021174  lea     ecx, [rsi+42h]
0x140021177  mov     edx, eax
0x140021179  call    cs:__imp_ExAllocatePool2
0x140021180  nop     dword ptr [rax+rax+00h]
0x140021185  mov     rsi, rax
0x140021188  test    rax, rax
0x14002118b  jnz     short loc_140021197
0x14002118d  mov     ebx, 0C000009Ah
0x140021192  jmp     loc_1400212D3
0x140021197  mov     rcx, [r14+8]; DeviceObject
0x14002119b  lea     rax, [rbp+var_40]
0x14002119f  mov     r9d, edi; Length
0x1400211a2  mov     [rsp+70h+var_50], rax; PLARGE_INTEGER
0x1400211a7  mov     r8, rsi; Buffer
0x1400211aa  mov     qword ptr [rbp+var_40], 0
0x1400211b2  mov     edx, 3; MajorFunction
0x1400211b7  call    ?PmSendIO@@YAJPEAU_DEVICE_OBJECT@@KPEAXKPEAT_LARGE_INTEGER@@@Z; PmSendIO(_DEVICE_OBJECT *,ulong,void *,ulong,_LARGE_INTEGER *)
0x1400211bc  mov     ebx, eax
0x1400211be  test    eax, eax
0x1400211c0  js      loc_14002129B
0x1400211c6  lea     rcx, [rbp+var_40]
0x1400211ca  mov     r9d, edi; Length
0x1400211cd  mov     [rsp+70h+var_50], rcx; PLARGE_INTEGER
0x1400211d2  lea     r8, [rdi+rsi]; Buffer
0x1400211d6  mov     rcx, [r15+8]; DeviceObject
0x1400211da  mov     edx, 3; MajorFunction
0x1400211df  call    ?PmSendIO@@YAJPEAU_DEVICE_OBJECT@@KPEAXKPEAT_LARGE_INTEGER@@@Z; PmSendIO(_DEVICE_OBJECT *,ulong,void *,ulong,_LARGE_INTEGER *)
0x1400211e4  mov     ebx, eax
0x1400211e6  test    eax, eax
0x1400211e8  js      loc_14002129B
0x1400211ee  movzx   ebx, word ptr [rsi+1BCh]
0x1400211f5  lea     rcx, [rbp+var_30]; struct _GUID *
0x1400211f9  call    ?PmUuidCreate@@YAXPEAU_GUID@@@Z; PmUuidCreate(_GUID *)
0x1400211fe  movzx   eax, word ptr [rbp+var_30.Data1]
0x140021202  xor     ax, word ptr [rbp+var_30.Data1+2]
0x140021206  xor     ax, [rbp+var_30.Data2]
0x14002120a  xor     ax, [rbp+var_30.Data3]
0x14002120e  xor     ax, word ptr [rbp+var_30.Data4]
0x140021212  xor     ax, word ptr [rbp+var_30.Data4+2]
0x140021216  xor     ax, word ptr [rbp+var_30.Data4+4]
0x14002121a  xor     ax, word ptr [rbp+var_30.Data4+6]
0x14002121e  mov     [rsi+1BCh], ax
0x140021225  cmp     ax, bx
0x140021228  jz      short loc_1400211F5
0x14002122a  mov     rcx, [r14+8]; DeviceObject
0x14002122e  lea     rax, [rbp+var_40]
0x140021232  mov     r9d, edi; Length
0x140021235  mov     [rsp+70h+var_50], rax; PLARGE_INTEGER
0x14002123a  mov     r8, rsi; Buffer
0x14002123d  mov     edx, 4; MajorFunction
0x140021242  call    ?PmSendIO@@YAJPEAU_DEVICE_OBJECT@@KPEAXKPEAT_LARGE_INTEGER@@@Z; PmSendIO(_DEVICE_OBJECT *,ulong,void *,ulong,_LARGE_INTEGER *)
0x140021247  mov     ebx, eax
0x140021249  test    eax, eax
0x14002124b  js      short loc_14002129B
0x14002124d  lea     rcx, [rbp+var_40]
0x140021251  mov     r9d, edi; Length
0x140021254  mov     [rsp+70h+var_50], rcx; PLARGE_INTEGER
0x140021259  lea     eax, [rdi+rdi]
0x14002125c  mov     rcx, [r15+8]; DeviceObject
0x140021260  add     rax, rsi
0x140021263  mov     r8, rax; Buffer
0x140021266  mov     [rbp+Source2], rax
0x14002126a  mov     edx, 3; MajorFunction
0x14002126f  call    ?PmSendIO@@YAJPEAU_DEVICE_OBJECT@@KPEAXKPEAT_LARGE_INTEGER@@@Z; PmSendIO(_DEVICE_OBJECT *,ulong,void *,ulong,_LARGE_INTEGER *)
0x140021274  mov     ebx, eax
0x140021276  test    eax, eax
0x140021278  js      short loc_14002129B
0x14002127a  mov     rdx, [rbp+Source2]; Source2
0x14002127e  lea     rcx, [rdi+rsi]; Source1
0x140021282  mov     r8, rdi; Length
0x140021285  call    cs:__imp_RtlCompareMemory
0x14002128c  nop     dword ptr [rax+rax+00h]
0x140021291  cmp     rax, rdi
0x140021294  jz      short loc_14002129B
0x140021296  mov     byte ptr [r13+0], 1
0x14002129b  xor     edx, edx; Tag
0x14002129d  mov     rcx, rsi; P
0x1400212a0  call    cs:__imp_ExFreePoolWithTag
0x1400212a7  nop     dword ptr [rax+rax+00h]
0x1400212ac  xor     esi, esi
0x1400212ae  test    ebx, ebx
0x1400212b0  js      short loc_1400212D3
0x1400212b2  jmp     short loc_1400212B6
0x1400212b4  mov     ebx, esi
0x1400212b6  mov     rdx, r15; struct _DEVICE_EXTENSION *
0x1400212b9  mov     rcx, r14; struct _DEVICE_EXTENSION *
0x1400212bc  mov     r8d, 8004003Bh
0x1400212c2  cmp     [r13+0], sil
0x1400212c6  jnz     short loc_1400212CE
0x1400212c8  mov     r8d, 8004003Ah; int
0x1400212ce  call    ?PmLogError@@YAXPEAU_DEVICE_EXTENSION@@0J@Z; PmLogError(_DEVICE_EXTENSION *,_DEVICE_EXTENSION *,long)
0x1400212d3  mov     eax, ebx
0x1400212d5  mov     rcx, [rbp-8]
0x1400212d9  xor     rcx, rsp; StackCookie
0x1400212dc  call    __security_check_cookie
0x1400212e1  mov     rbx, [rsp+70h+arg_18]
0x1400212e9  add     rsp, 70h
0x1400212ed  pop     r15
0x1400212ef  pop     r14
0x1400212f1  pop     r13
0x1400212f3  pop     r12
0x1400212f5  pop     rdi
0x1400212f6  pop     rsi
0x1400212f7  pop     rbp
0x1400212f8  retn
```
