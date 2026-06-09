# SdpGetServiceGuidsFromRfcommPort

- ea: `0x14003468c`
- end: `0x1400349f4`
- name: `SdpGetServiceGuidsFromRfcommPort`
- size: `872`
- prototype: `__int64 __fastcall(int, int, int, struct _GUID **, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001b970`

## callees

- `0x14001fb74`
- `0x14001fb90`
- `0x14001fba4`
- `0x140034420`
- `0x1400344f4`
- `0x14003468c`
- `0x140034a80`
- `0x1400358f8`
- `0x140035ab8`
- `0x140036444`
- `0x1400365d0`
- `0x140036754`
- `0x1400367e4`

## pseudocode

```c
__int64 __fastcall SdpGetServiceGuidsFromRfcommPort(int a1, int a2, int a3, struct _GUID **a4, unsigned int *a5)
{
  int v5; // ebx
  int v6; // r14d
  int ServiceGuidsFromServiceTree; // edi
  char v8; // si
  unsigned __int8 *v9; // r15
  __int64 v10; // rdx
  unsigned __int8 v11; // al
  __int64 v12; // rbx
  int v13; // r8d
  __int64 v14; // r12
  __int64 Pool; // rsi
  unsigned int v16; // r14d
  int v17; // r13d
  __int64 v18; // rax
  struct _SDP_TREE_ROOT_NODE *v19; // rbx
  char *v21; // rdx
  unsigned int i; // r8d
  __int64 v23; // rcx
  _QWORD *v24; // rcx
  unsigned int v25; // edx
  const struct _GUID *v26; // rdx
  struct _SDP_NODE **LowPart; // rax
  struct _SDP_NODE *v28; // rcx
  __int64 v29; // rcx
  char *v30; // [rsp+20h] [rbp-48h]
  char *v31; // [rsp+20h] [rbp-48h]
  __int64 v32; // [rsp+28h] [rbp-40h]
  __int64 v33; // [rsp+30h] [rbp-38h]
  PSDP_NODE Attribute; // [rsp+38h] [rbp-30h] BYREF
  struct _SDP_NODE *v35; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v36; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int8 *v37; // [rsp+50h] [rbp-18h] BYREF
  __int64 v38; // [rsp+58h] [rbp-10h] BYREF

  *a4 = 0;
  v5 = a2;
  v6 = a1;
  *a5 = 0;
  LOBYTE(v33) = 0;
  ServiceGuidsFromServiceTree = SdpValidateStream(a1, a2, 0, 0, 0);
  v37 = 0;
  v8 = 0;
  v36 = 0;
  LODWORD(v9) = 0;
  if ( ServiceGuidsFromServiceTree < 0 )
    return (unsigned int)ServiceGuidsFromServiceTree;
  while ( !v8 )
  {
    SdpGetNextElement(v6, v5, (_DWORD)v9, (unsigned int)&v37, (__int64)&v36);
    v9 = v37;
    if ( !v37 )
      goto LABEL_21;
    LOBYTE(v10) = *v37;
    v11 = *v37;
    LODWORD(Attribute) = 0;
    LODWORD(v35) = 0;
    if ( (v11 & 0xF8) == 0x30 )
    {
      v12 = v36;
      LOBYTE(v10) = v10 & 7;
      ((void (__fastcall *)(unsigned __int8 *, __int64, PSDP_NODE *, struct _SDP_NODE **, char *, __int64, __int64))SdpRetrieveVariableSize)(
        v37 + 1,
        v10,
        &Attribute,
        &v35,
        v30,
        v32,
        v33);
      if ( v12 != (unsigned int)v35 + (unsigned int)Attribute + 1LL )
        goto LABEL_19;
      Attribute = 0;
      v13 = 0;
      LODWORD(v35) = 0;
      while ( 1 )
      {
        SdpGetNextElement((_DWORD)v9, v12, v13, (unsigned int)&Attribute, (__int64)&v35);
        if ( !Attribute )
          break;
        if ( ((__int64)Attribute->hdr.Link.Flink & 0xF8) == 8
          && g_IndexToDataSize[(__int64)Attribute->hdr.Link.Flink & 7] == 2 )
        {
          SdpGetNextElement((_DWORD)v9, v12, (_DWORD)Attribute, (unsigned int)&Attribute, (__int64)&v35);
          v13 = (int)Attribute;
          if ( Attribute )
            continue;
        }
        goto LABEL_19;
      }
      LOWORD(v35) = 0;
      if ( (int)SdpVerifyServiceRecord(v9, v12) < 0 )
        goto LABEL_19;
      v38 = 0;
      LODWORD(Attribute) = 0;
      LODWORD(v35) = 0;
      if ( (int)SdpValidateStream((_DWORD)v9, v12, (unsigned int)&Attribute, (unsigned int)&v35, (__int64)&v38) < 0 )
        goto LABEL_19;
      v14 = (unsigned int)((_DWORD)Attribute + 1);
      Pool = SdppAllocatePool(16);
      if ( Pool )
      {
        v16 = 72 * v14;
        if ( (unsigned __int64)(72 * v14) > 0xFFFFFFFF )
          goto LABEL_42;
        v17 = (int)v35;
        if ( v16 + (unsigned int)v35 < v16
          || (v18 = SdppAllocatePool(v16 + (unsigned int)v35), (v19 = (struct _SDP_TREE_ROOT_NODE *)v18) == 0) )
        {
          SdpFreePool(Pool);
          v8 = v33;
          goto LABEL_18;
        }
        v21 = 0;
        if ( v17 )
          v21 = (char *)(v18 + v16);
        *(_QWORD *)Pool = v18;
        *(_DWORD *)(Pool + 8) = v14;
        for ( i = 0; i < (unsigned int)v14; v24[7] = Pool )
        {
          v23 = i++;
          v24 = (_QWORD *)(v18 + (v23 << 6));
          v24[1] = v24;
          *v24 = v24;
        }
        LOBYTE(v32) = 1;
        v31 = v21;
        v25 = v36;
        *(_DWORD *)(v18 + 16) = 33;
        *(_QWORD *)(v18 + 8) = v18;
        *(_QWORD *)v18 = v18;
        if ( SdppStreamToNode(v9, v25, (struct _SDP_TREE_ROOT_NODE *)v18, (struct _SDP_NODE *)(v18 + 64), v31) )
        {
          Attribute = 0;
          if ( SdpFindAttributeInTree(v19, 4u, &Attribute) >= 0
            && (v35 = 0, (int)SdppGetDescriptorFromDescriptorList(Attribute, v26, &v35) >= 0)
            && (LowPart = (struct _SDP_NODE **)v35->u.int128.LowPart,
                v28 = *LowPart,
                *LowPart != (struct _SDP_NODE *)&v35->u)
            && (SDP_NODE_DATA *)v28->hdr.Link.Flink == &v35->u
            && v28->hdr.SpecificType == 16
            && v28->u.uint8 == a3 )
          {
            v8 = 1;
            LOBYTE(v33) = 1;
            ServiceGuidsFromServiceTree = SdppExtractServiceGuidsFromServiceTree(v19, a4, a5);
          }
          else
          {
            v8 = v33;
          }
          if ( v19->RootNode.hdr.Type != 33 )
            goto LABEL_18;
          SdppFreeTreeWorker(v19);
          Pool = (__int64)v19->RootNode.Reserved;
          if ( Pool )
          {
            if ( !(unsigned int)SdpInterlockedDecrement(Pool + 8) )
            {
              SdpFreePool(*(_QWORD *)Pool);
LABEL_42:
              v29 = Pool;
LABEL_43:
              SdpFreePool(v29);
            }
            v8 = v33;
LABEL_18:
            v6 = a1;
LABEL_19:
            v5 = a2;
            goto LABEL_20;
          }
        }
        else
        {
          SdpFreePool(Pool);
        }
        v29 = (__int64)v19;
        goto LABEL_43;
      }
      v8 = v33;
      goto LABEL_19;
    }
LABEL_20:
    if ( ServiceGuidsFromServiceTree < 0 )
    {
LABEL_21:
      if ( ServiceGuidsFromServiceTree < 0 )
        return (unsigned int)ServiceGuidsFromServiceTree;
      break;
    }
  }
  if ( !v8 )
    return (unsigned int)-1073741275;
  return (unsigned int)ServiceGuidsFromServiceTree;
}

```

## disassembly

```asm
0x14003468c  mov     rax, rsp
0x14003468f  mov     [rax+20h], r9
0x140034693  mov     [rax+18h], r8d
0x140034697  mov     [rax+10h], edx
0x14003469a  mov     [rax+8], rcx
0x14003469e  push    rbp
0x14003469f  push    rbx
0x1400346a0  push    rsi
0x1400346a1  push    rdi
0x1400346a2  push    r12
0x1400346a4  push    r13
0x1400346a6  push    r14
0x1400346a8  push    r15
0x1400346aa  mov     rbp, rsp
0x1400346ad  sub     rsp, 68h
0x1400346b1  mov     rax, [rbp+arg_20]
0x1400346b5  xor     r13d, r13d
0x1400346b8  mov     [r9], r13
0x1400346bb  xor     r8d, r8d
0x1400346be  xor     r9d, r9d
0x1400346c1  mov     [rsp+68h+var_48], r13
0x1400346c6  mov     ebx, edx
0x1400346c8  mov     r14, rcx
0x1400346cb  mov     [rax], r13d
0x1400346ce  call    SdpValidateStream
0x1400346d3  mov     byte ptr [rbp+var_38], r13b
0x1400346d7  mov     edi, eax
0x1400346d9  mov     [rbp+var_18], r13
0x1400346dd  mov     sil, r13b
0x1400346e0  mov     [rbp+var_20], r13d
0x1400346e4  mov     r15d, r13d
0x1400346e7  test    eax, eax
0x1400346e9  js      loc_14003489D
0x1400346ef  test    sil, sil
0x1400346f2  jnz     loc_140034892
0x1400346f8  lea     rax, [rbp+var_20]
0x1400346fc  mov     r8, r15
0x1400346ff  lea     r9, [rbp+var_18]
0x140034703  mov     [rsp+68h+var_48], rax
0x140034708  mov     edx, ebx
0x14003470a  mov     rcx, r14
0x14003470d  call    SdpGetNextElement
0x140034712  mov     r15, [rbp+var_18]
0x140034716  test    r15, r15
0x140034719  jz      loc_14003488E
0x14003471f  mov     dl, [r15]
0x140034722  mov     al, dl
0x140034724  mov     dword ptr [rbp+Attribute], r13d
0x140034728  and     al, 0F8h
0x14003472a  mov     dword ptr [rbp+var_28], r13d
0x14003472e  cmp     al, 30h ; '0'
0x140034730  jnz     loc_140034886
0x140034736  mov     ebx, [rbp+var_20]
0x140034739  lea     rcx, [r15+1]
0x14003473d  and     dl, 7
0x140034740  lea     r9, [rbp+var_28]
0x140034744  lea     r8, [rbp+Attribute]
0x140034748  call    SdpRetrieveVariableSize
0x14003474d  mov     ecx, dword ptr [rbp+Attribute]
0x140034750  mov     edx, dword ptr [rbp+var_28]
0x140034753  inc     rcx
0x140034756  add     rcx, rdx
0x140034759  cmp     rbx, rcx
0x14003475c  jnz     loc_140034883
0x140034762  mov     [rbp+Attribute], r13
0x140034766  xor     r8d, r8d
0x140034769  mov     dword ptr [rbp+var_28], r13d
0x14003476d  jmp     short loc_1400347BB
0x14003476f  movzx   edx, byte ptr [rcx]
0x140034772  mov     al, dl
0x140034774  and     al, 0F8h
0x140034776  cmp     al, 8
0x140034778  jnz     loc_140034883
0x14003477e  mov     eax, edx
0x140034780  lea     rdx, g_IndexToDataSize
0x140034787  and     eax, 7
0x14003478a  cmp     dword ptr [rdx+rax*4], 2
0x14003478e  jnz     loc_140034883
0x140034794  lea     rax, [rbp+var_28]
0x140034798  mov     r8, rcx
0x14003479b  mov     rcx, r15
0x14003479e  mov     [rsp+68h+var_48], rax
0x1400347a3  lea     r9, [rbp+Attribute]
0x1400347a7  mov     edx, ebx
0x1400347a9  call    SdpGetNextElement
0x1400347ae  mov     r8, [rbp+Attribute]
0x1400347b2  test    r8, r8
0x1400347b5  jz      loc_140034883
0x1400347bb  lea     rax, [rbp+var_28]
0x1400347bf  mov     edx, ebx
0x1400347c1  lea     r9, [rbp+Attribute]
0x1400347c5  mov     [rsp+68h+var_48], rax
0x1400347ca  mov     rcx, r15
0x1400347cd  call    SdpGetNextElement
0x1400347d2  mov     rcx, [rbp+Attribute]
0x1400347d6  test    rcx, rcx
0x1400347d9  jnz     short loc_14003476F
0x1400347db  lea     r9, [rbp+var_28]
0x1400347df  mov     word ptr [rbp+var_28], r13w
0x1400347e4  mov     edx, ebx; unsigned int
0x1400347e6  mov     rcx, r15; unsigned __int8 *
0x1400347e9  call    SdpVerifyServiceRecord
0x1400347ee  test    eax, eax
0x1400347f0  js      loc_140034883
0x1400347f6  lea     rax, [rbp+var_10]
0x1400347fa  mov     [rbp+var_10], r13
0x1400347fe  lea     r9, [rbp+var_28]
0x140034802  mov     [rsp+68h+var_48], rax
0x140034807  lea     r8, [rbp+Attribute]
0x14003480b  mov     dword ptr [rbp+Attribute], r13d
0x14003480f  mov     edx, ebx
0x140034811  mov     dword ptr [rbp+var_28], r13d
0x140034815  mov     rcx, r15
0x140034818  call    SdpValidateStream
0x14003481d  test    eax, eax
0x14003481f  js      short loc_140034883
0x140034821  mov     r12d, dword ptr [rbp+Attribute]
0x140034825  mov     ecx, 10h
0x14003482a  inc     r12d
0x14003482d  call    SdppAllocatePool
0x140034832  mov     rsi, rax
0x140034835  test    rax, rax
0x140034838  jz      loc_1400349EB
0x14003483e  lea     r14, [r12+r12*8]
0x140034842  mov     eax, 0FFFFFFFFh
0x140034847  shl     r14, 3
0x14003484b  cmp     r14, rax
0x14003484e  ja      loc_1400349CD
0x140034854  mov     r13d, dword ptr [rbp+var_28]
0x140034858  lea     eax, [r14+r13]
0x14003485c  cmp     eax, r14d
0x14003485f  jb      short loc_140034870
0x140034861  mov     ecx, eax
0x140034863  call    SdppAllocatePool
0x140034868  mov     rbx, rax
0x14003486b  test    rax, rax
0x14003486e  jnz     short loc_1400348B1
0x140034870  mov     rcx, rsi
0x140034873  call    SdpFreePool
0x140034878  mov     sil, byte ptr [rbp+var_38]
0x14003487c  xor     r13d, r13d
0x14003487f  mov     r14, [rbp+arg_0]
0x140034883  mov     ebx, [rbp+arg_8]
0x140034886  test    edi, edi
0x140034888  jns     loc_1400346EF
0x14003488e  test    edi, edi
0x140034890  js      short loc_14003489D
0x140034892  test    sil, sil
0x140034895  mov     eax, 0C0000225h
0x14003489a  cmovz   edi, eax
0x14003489d  mov     eax, edi
0x14003489f  add     rsp, 68h
0x1400348a3  pop     r15
0x1400348a5  pop     r14
0x1400348a7  pop     r13
0x1400348a9  pop     r12
0x1400348ab  pop     rdi
0x1400348ac  pop     rsi
0x1400348ad  pop     rbx
0x1400348ae  pop     rbp
0x1400348af  retn
0x1400348b1  xor     edx, edx
0x1400348b3  test    r13d, r13d
0x1400348b6  jz      short loc_1400348BE
0x1400348b8  mov     edx, r14d
0x1400348bb  add     rdx, rbx
0x1400348be  xor     r13d, r13d
0x1400348c1  mov     [rsi], rbx
0x1400348c4  mov     [rsi+8], r12d
0x1400348c8  mov     r8d, r13d
0x1400348cb  test    r12d, r12d
0x1400348ce  jz      short loc_1400348ED
0x1400348d0  mov     ecx, r8d
0x1400348d3  inc     r8d
0x1400348d6  shl     rcx, 6
0x1400348da  add     rcx, rbx
0x1400348dd  mov     [rcx+8], rcx
0x1400348e1  mov     [rcx], rcx
0x1400348e4  mov     [rcx+38h], rsi
0x1400348e8  cmp     r8d, r12d
0x1400348eb  jb      short loc_1400348D0
0x1400348ed  mov     byte ptr [rsp+68h+var_40], 1; unsigned __int8
0x1400348f2  lea     r9, [rax+40h]; struct _SDP_NODE *
0x1400348f6  mov     [rsp+68h+var_48], rdx; char *
0x1400348fb  mov     r12d, 21h ; '!'
0x140034901  mov     edx, [rbp+var_20]; unsigned int
0x140034904  mov     r8, rbx; struct _SDP_TREE_ROOT_NODE *
0x140034907  mov     rcx, r15; unsigned __int8 *
0x14003490a  mov     [rax+10h], r12d
0x14003490e  mov     [rax+8], rbx
0x140034912  mov     [rax], rbx
0x140034915  call    ?SdppStreamToNode@@YAPEAU_SDP_NODE@@PEAEKPEAU_SDP_TREE_ROOT_NODE@@PEAU1@PEADE@Z; SdppStreamToNode(uchar *,ulong,_SDP_TREE_ROOT_NODE *,_SDP_NODE *,char *,uchar)
0x14003491a  test    rax, rax
0x14003491d  jz      loc_1400349DE
0x140034923  lea     edx, [r12-1Dh]; AttribId
0x140034928  mov     [rbp+Attribute], r13
0x14003492c  lea     r8, [rbp+Attribute]; Attribute
0x140034930  mov     rcx, rbx; Tree
0x140034933  call    SdpFindAttributeInTree
0x140034938  test    eax, eax
0x14003493a  js      short loc_140034998
0x14003493c  mov     rcx, [rbp+Attribute]; struct _SDP_NODE *
0x140034940  lea     r8, [rbp+var_28]; struct _SDP_NODE **
0x140034944  mov     [rbp+var_28], r13
0x140034948  call    ?SdppGetDescriptorFromDescriptorList@@YAJPEAU_SDP_NODE@@AEBU_GUID@@PEAPEAU1@@Z; SdppGetDescriptorFromDescriptorList(_SDP_NODE *,_GUID const &,_SDP_NODE * *)
0x14003494d  test    eax, eax
0x14003494f  js      short loc_140034998
0x140034951  mov     rdx, [rbp+var_28]
0x140034955  add     rdx, 20h ; ' '
0x140034959  mov     rax, [rdx]
0x14003495c  mov     rcx, [rax]
0x14003495f  cmp     rcx, rdx
0x140034962  jz      short loc_140034998
0x140034964  cmp     [rcx], rdx
0x140034967  jnz     short loc_140034998
0x140034969  lea     eax, [r12-11h]
0x14003496e  cmp     ax, [rcx+12h]
0x140034972  jnz     short loc_140034998
0x140034974  movzx   eax, byte ptr [rcx+20h]
0x140034978  cmp     eax, [rbp+arg_10]
0x14003497b  jnz     short loc_140034998
0x14003497d  mov     r8, [rbp+arg_20]; unsigned int *
0x140034981  mov     sil, 1
0x140034984  mov     rdx, [rbp+arg_18]; struct _GUID **
0x140034988  mov     rcx, rbx; struct _SDP_TREE_ROOT_NODE *
0x14003498b  mov     byte ptr [rbp+var_38], sil
0x14003498f  call    ?SdppExtractServiceGuidsFromServiceTree@@YAJPEAU_SDP_TREE_ROOT_NODE@@PEAPEAU_GUID@@PEAK@Z; SdppExtractServiceGuidsFromServiceTree(_SDP_TREE_ROOT_NODE *,_GUID * *,ulong *)
0x140034994  mov     edi, eax
0x140034996  jmp     short loc_14003499C
0x140034998  mov     sil, byte ptr [rbp+var_38]
0x14003499c  cmp     [rbx+10h], r12w
0x1400349a1  jnz     loc_14003487F
0x1400349a7  mov     rcx, rbx
0x1400349aa  call    SdppFreeTreeWorker
0x1400349af  mov     rsi, [rbx+38h]
0x1400349b3  test    rsi, rsi
0x1400349b6  jz      short loc_1400349E6
0x1400349b8  lea     rcx, [rsi+8]
0x1400349bc  call    SdpInterlockedDecrement
0x1400349c1  test    eax, eax
0x1400349c3  jnz     short loc_1400349D5
0x1400349c5  mov     rcx, [rsi]
0x1400349c8  call    SdpFreePool
0x1400349cd  mov     rcx, rsi
0x1400349d0  call    SdpFreePool
0x1400349d5  mov     sil, byte ptr [rbp+var_38]
0x1400349d9  jmp     loc_14003487F
0x1400349de  mov     rcx, rsi
0x1400349e1  call    SdpFreePool
0x1400349e6  mov     rcx, rbx
0x1400349e9  jmp     short loc_1400349D0
0x1400349eb  mov     sil, byte ptr [rbp+var_38]
0x1400349ef  jmp     loc_140034883
```
