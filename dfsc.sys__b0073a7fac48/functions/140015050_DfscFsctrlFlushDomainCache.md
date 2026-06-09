# DfscFsctrlFlushDomainCache

- ea: `0x140015050`
- end: `0x140015203`
- name: `DfscFsctrlFlushDomainCache`
- size: `435`
- prototype: `__int64 __fastcall(__int64, WCHAR *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140014910`

## callees

- `0x140001010`
- `0x140001744`
- `0x140002fcc`
- `0x140015050`
- `0x1400199e4`
- `0x14001c2e4`
- `0x14001d090`
- `0x140022cd8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400151da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400151da`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400151ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400151ce`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x140015156`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x140015156`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001513a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001513a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015125`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015125`

## pseudocode

```c
__int64 __fastcall DfscFsctrlFlushDomainCache(__int64 a1, WCHAR *a2, unsigned int a3)
{
  __int64 v6; // rdx
  int ContainerContextFromIrp; // edi
  struct _UNICODE_PREFIX_TABLE *DomainCache; // rax
  unsigned int v9; // ebx
  unsigned int i; // ecx
  __int64 v11; // rbx
  struct _ERESOURCE *v12; // rsi
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  struct _RTL_SPLAY_LINKS **p_RightChild; // rbx
  UNICODE_STRING FullName; // [rsp+30h] [rbp-28h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v17 = 0;
  FullName = 0;
  if ( a3 >= 2 && (a3 & 1) == 0 && a3 <= 0xFFFE && a2 && *a2 )
  {
    ContainerContextFromIrp = DfscGetContainerContextFromIrp(a1, &v17);
    if ( ContainerContextFromIrp >= 0 )
    {
      if ( a3 == 2 && *a2 == 42 )
      {
        DomainCache = (struct _UNICODE_PREFIX_TABLE *)DfscGetDomainCache(v17, v6);
        DfscCachePurge(DomainCache);
        return (unsigned int)DfscPopulateDomainNameCache(a1, v17);
      }
      else
      {
        v9 = a3 >> 1;
        for ( i = 0; i < v9; ++i )
        {
          if ( !a2[i] )
            break;
        }
        FullName.Buffer = a2;
        FullName.Length = 2 * i;
        FullName.MaximumLength = 2 * i;
        v11 = DfscGetDomainCache(v17, v6);
        KeEnterCriticalRegion();
        v12 = (struct _ERESOURCE *)(v11 + 56);
        ExAcquireResourceExclusiveLite((PERESOURCE)(v11 + 56), 1u);
        ContainerContextFromIrp = -1073741766;
        UnicodePrefix = RtlFindUnicodePrefix((PUNICODE_PREFIX_TABLE)v11, &FullName, 0);
        if ( UnicodePrefix )
        {
          p_RightChild = &UnicodePrefix[-2].Links.RightChild;
          if ( (BYTE4(UnicodePrefix[-2].Prefix) & 1) != 0 && *((_WORD *)p_RightChild + 72) == FullName.Length )
          {
            ContainerContextFromIrp = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                36,
                WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids,
                p_RightChild,
                a1);
            }
            DfscRmUnlinkReferral(p_RightChild);
            DfscRmDereferenceReferral(p_RightChild);
          }
        }
        ExReleaseResourceLite(v12);
        KeLeaveCriticalRegion();
      }
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)ContainerContextFromIrp;
}

```

## disassembly

```asm
0x140015050  mov     rax, rsp
0x140015053  mov     [rax+8], rbx
0x140015057  mov     [rax+18h], rbp
0x14001505b  push    rsi
0x14001505c  push    rdi
0x14001505d  push    r14
0x14001505f  sub     rsp, 40h
0x140015063  xor     r14d, r14d
0x140015066  xorps   xmm0, xmm0
0x140015069  mov     [rax+10h], r14
0x14001506d  mov     ebx, r8d
0x140015070  mov     rsi, rdx
0x140015073  mov     rbp, rcx
0x140015076  movups  xmmword ptr [rax-28h], xmm0
0x14001507a  cmp     r8d, 2
0x14001507e  jb      loc_1400151E8
0x140015084  test    bl, 1
0x140015087  jnz     loc_1400151E8
0x14001508d  cmp     ebx, 0FFFEh
0x140015093  ja      loc_1400151E8
0x140015099  test    rdx, rdx
0x14001509c  jz      loc_1400151E8
0x1400150a2  cmp     [rdx], r14w
0x1400150a6  jz      loc_1400151E8
0x1400150ac  lea     rdx, [rax+10h]
0x1400150b0  call    DfscGetContainerContextFromIrp
0x1400150b5  mov     edi, eax
0x1400150b7  test    eax, eax
0x1400150b9  js      loc_1400151ED
0x1400150bf  cmp     ebx, 2
0x1400150c2  jnz     short loc_1400150F0
0x1400150c4  cmp     word ptr [rsi], 2Ah ; '*'
0x1400150c8  jnz     short loc_1400150F0
0x1400150ca  mov     rcx, [rsp+58h+arg_8]
0x1400150cf  call    DfscGetDomainCache
0x1400150d4  mov     rcx, rax; PrefixTable
0x1400150d7  call    DfscCachePurge
0x1400150dc  mov     rdx, [rsp+58h+arg_8]
0x1400150e1  mov     rcx, rbp
0x1400150e4  call    DfscPopulateDomainNameCache
0x1400150e9  mov     edi, eax
0x1400150eb  jmp     loc_1400151ED
0x1400150f0  shr     ebx, 1
0x1400150f2  mov     ecx, r14d
0x1400150f5  jz      short loc_140015106
0x1400150f7  mov     eax, ecx
0x1400150f9  cmp     [rsi+rax*2], r14w
0x1400150fe  jz      short loc_140015106
0x140015100  inc     ecx
0x140015102  cmp     ecx, ebx
0x140015104  jb      short loc_1400150F7
0x140015106  add     cx, cx
0x140015109  mov     [rsp+58h+FullName.Buffer], rsi
0x14001510e  mov     [rsp+58h+FullName.Length], cx
0x140015113  mov     [rsp+58h+FullName.MaximumLength], cx
0x140015118  mov     rcx, [rsp+58h+arg_8]
0x14001511d  call    DfscGetDomainCache
0x140015122  mov     rbx, rax
0x140015125  call    cs:__imp_KeEnterCriticalRegion
0x14001512c  nop     dword ptr [rax+rax+00h]
0x140015131  lea     rsi, [rbx+38h]
0x140015135  mov     dl, 1; Wait
0x140015137  mov     rcx, rsi; Resource
0x14001513a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140015141  nop     dword ptr [rax+rax+00h]
0x140015146  xor     r8d, r8d; CaseInsensitiveIndex
0x140015149  lea     rdx, [rsp+58h+FullName]; FullName
0x14001514e  mov     rcx, rbx; PrefixTable
0x140015151  mov     edi, 0C000003Ah
0x140015156  call    cs:__imp_RtlFindUnicodePrefix
0x14001515d  nop     dword ptr [rax+rax+00h]
0x140015162  test    rax, rax
0x140015165  jz      short loc_1400151CB
0x140015167  lea     rbx, [rax-48h]
0x14001516b  test    byte ptr [rbx+0Ch], 1
0x14001516f  jz      short loc_1400151CB
0x140015171  movzx   eax, [rsp+58h+FullName.Length]
0x140015176  cmp     [rbx+90h], ax
0x14001517d  jnz     short loc_1400151CB
0x14001517f  mov     edi, r14d
0x140015182  mov     rcx, cs:WPP_GLOBAL_Control
0x140015189  lea     rax, WPP_GLOBAL_Control
0x140015190  cmp     rcx, rax
0x140015193  jz      short loc_1400151BB
0x140015195  test    dword ptr [rcx+2Ch], 200000h
0x14001519c  jz      short loc_1400151BB
0x14001519e  mov     rcx, [rcx+18h]
0x1400151a2  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x1400151a9  mov     edx, 24h ; '$'
0x1400151ae  mov     [rsp+58h+var_38], rbp
0x1400151b3  mov     r9, rbx
0x1400151b6  call    WPP_SF_qq
0x1400151bb  mov     rcx, rbx
0x1400151be  call    DfscRmUnlinkReferral
0x1400151c3  mov     rcx, rbx; P
0x1400151c6  call    DfscRmDereferenceReferral
0x1400151cb  mov     rcx, rsi; Resource
0x1400151ce  call    cs:__imp_ExReleaseResourceLite
0x1400151d5  nop     dword ptr [rax+rax+00h]
0x1400151da  call    cs:__imp_KeLeaveCriticalRegion
0x1400151e1  nop     dword ptr [rax+rax+00h]
0x1400151e6  jmp     short loc_1400151ED
0x1400151e8  mov     edi, 0C000000Dh
0x1400151ed  mov     rbx, [rsp+58h+arg_0]
0x1400151f2  mov     eax, edi
0x1400151f4  mov     rbp, [rsp+58h+arg_10]
0x1400151f9  add     rsp, 40h
0x1400151fd  pop     r14
0x1400151ff  pop     rdi
0x140015200  pop     rsi
0x140015201  retn
```
