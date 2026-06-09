# CWmiObjPath::_CreateCscItemObject(IWbemServices *,IWbemContext *,IOfflineFilesCache *,IWbemClassObject * *)

- ea: `0x1800228d8`
- end: `0x1800229a5`
- name: `?_CreateCscItemObject@CWmiObjPath@@AEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIOfflineFilesCache@@PEAPEAUIWbemClassObject@@@Z`
- size: `205`
- prototype: `__int64 __usercall@<rax>(CWmiObjPath *__hidden this@<rcx>, struct IWbemServices *@<rdx>, struct IWbemContext *@<r8>, struct IOfflineFilesCache *@<r9>, struct IWbemClassObject **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002273c`

## callees

- `0x180016920`
- `0x180016b74`
- `0x18001d574`
- `0x1800228d8`
- `0x180022b4c`
- `0x18002c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180022903`
- `OLEAUT32!__imp_VariantInit` at `0x180022903`
- `OLEAUT32!__imp_VariantClear` at `0x180022992`
- `OLEAUT32!__imp_VariantClear` at `0x180022992`

## pseudocode

```c
__int64 __fastcall CWmiObjPath::_CreateCscItemObject(
        CWmiObjPath *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IOfflineFilesCache *a4,
        struct IWbemClassObject **a5)
{
  const unsigned __int16 *v9; // rdx
  int KeyValue; // ebx
  struct IOfflineFilesCacheVtbl *lpVtbl; // rax
  struct IOfflineFilesItem *v13; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-20h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  KeyValue = CWmiObjPath::_GetKeyValue(this, v9, &pvarg);
  if ( KeyValue >= 0 )
  {
    lpVtbl = a4->lpVtbl;
    v13 = 0;
    KeyValue = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, LONGLONG, _QWORD, struct IOfflineFilesItem **))lpVtbl->FindItem)(
                 a4,
                 pvarg.llVal,
                 0,
                 &v13);
    if ( KeyValue < 0 )
    {
      if ( KeyValue == -2147024894 )
        KeyValue = -2147217406;
    }
    else
    {
      CCscWmiItemObject::CCscWmiItemObject((CCscWmiItemObject *)v15, v13);
      KeyValue = CCscWmiObject::CreateWbemClassObject((CCscWmiObject *)v15, a2, a3, (BSTR *)a5);
      ((void (__fastcall *)(struct IOfflineFilesItem *))v13->lpVtbl->Release)(v13);
      CCscWmiItemObject::~CCscWmiItemObject((CCscWmiItemObject *)v15);
    }
  }
  VariantClear(&pvarg);
  return (unsigned int)KeyValue;
}

```

## disassembly

```asm
0x1800228d8  push    rbp
0x1800228da  push    rbx
0x1800228db  push    rsi
0x1800228dc  push    rdi
0x1800228dd  push    r14
0x1800228df  mov     rbp, rsp
0x1800228e2  sub     rsp, 70h
0x1800228e6  mov     rbx, rcx
0x1800228e9  xorps   xmm0, xmm0
0x1800228ec  xor     eax, eax
0x1800228ee  lea     rcx, [rbp+pvarg]; pvarg
0x1800228f2  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800228f6  mov     qword ptr [rbp+pvarg+10h], rax
0x1800228fa  mov     rdi, r9
0x1800228fd  mov     rsi, r8
0x180022900  mov     r14, rdx
0x180022903  call    cs:__imp_VariantInit
0x180022909  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x18002290d  mov     rcx, rbx; this
0x180022910  call    ?_GetKeyValue@CWmiObjPath@@AEAAJPEBGPEAUtagVARIANT@@@Z; CWmiObjPath::_GetKeyValue(ushort const *,tagVARIANT *)
0x180022915  mov     ebx, eax
0x180022917  test    eax, eax
0x180022919  js      short loc_18002298E
0x18002291b  mov     rax, [rdi]
0x18002291e  lea     r9, [rbp+var_40]
0x180022922  mov     rdx, qword ptr [rbp+pvarg+8]
0x180022926  xor     r8d, r8d
0x180022929  mov     rcx, rdi
0x18002292c  mov     [rbp+var_40], 0
0x180022934  mov     rax, [rax+50h]
0x180022938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002293d  mov     ebx, eax
0x18002293f  test    eax, eax
0x180022941  js      short loc_180022980
0x180022943  mov     rdx, [rbp+var_40]; struct IOfflineFilesItem *
0x180022947  lea     rcx, [rbp+var_20]; this
0x18002294b  call    ??0CCscWmiItemObject@@QEAA@PEAUIOfflineFilesItem@@@Z; CCscWmiItemObject::CCscWmiItemObject(IOfflineFilesItem *)
0x180022950  mov     r9, [rbp+arg_20]; struct IWbemClassObject **
0x180022954  lea     rcx, [rbp+var_20]; this
0x180022958  mov     r8, rsi; struct IWbemContext *
0x18002295b  mov     rdx, r14; struct IWbemServices *
0x18002295e  call    ?CreateWbemClassObject@CCscWmiObject@@QEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z; CCscWmiObject::CreateWbemClassObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)
0x180022963  mov     rcx, [rbp+var_40]
0x180022967  mov     ebx, eax
0x180022969  mov     rax, [rcx]
0x18002296c  mov     rax, [rax+10h]
0x180022970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022975  lea     rcx, [rbp+var_20]; this
0x180022979  call    ??1CCscWmiItemObject@@UEAA@XZ; CCscWmiItemObject::~CCscWmiItemObject(void)
0x18002297e  jmp     short loc_18002298E
0x180022980  cmp     ebx, 80070002h
0x180022986  mov     eax, 80041002h
0x18002298b  cmovz   ebx, eax
0x18002298e  lea     rcx, [rbp+pvarg]; pvarg
0x180022992  call    cs:__imp_VariantClear
0x180022998  mov     eax, ebx
0x18002299a  add     rsp, 70h
0x18002299e  pop     r14
0x1800229a0  pop     rdi
0x1800229a1  pop     rsi
0x1800229a2  pop     rbx
0x1800229a3  pop     rbp
0x1800229a4  retn
```
