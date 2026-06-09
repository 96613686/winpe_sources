# CObjectHeap::IndexEnumerationNext(void *,CFileName &,bool)

- ea: `0x180009920`
- end: `0x180009b72`
- name: `?IndexEnumerationNext@CObjectHeap@@QEAAJPEAXAEAVCFileName@@_N@Z`
- size: `594`
- prototype: `__int64 __fastcall(CObjectHeap *__hidden this, void *, struct CFileName *, bool)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008730`
- `0x180009b80`
- `0x18001dba8`
- `0x180027554`
- `0x180030a90`

## callees

- `0x1800012b8`
- `0x180009920`
- `0x180010fa0`

## import_xrefs

- `msvcrt!wcschr` at `0x180009a1c`
- `msvcrt!wcschr` at `0x180009a1c`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18000994f`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18000994f`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180009962`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180009962`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x180009970`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x180009970`
- `wbemcomn!GetMemLogObject` at `0x180009a67`
- `wbemcomn!GetMemLogObject` at `0x180009ae8`
- `wbemcomn!GetMemLogObject` at `0x180009b35`
- `wbemcomn!GetMemLogObject` at `0x180009a67`
- `wbemcomn!GetMemLogObject` at `0x180009ae8`
- `wbemcomn!GetMemLogObject` at `0x180009b35`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009a75`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009af8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009b40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009a75`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009af8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009b40`

## pseudocode

```c
__int64 __fastcall CObjectHeap::IndexEnumerationNext(CObjectHeap *this, CFlexArray *a2, const wchar_t **a3, char a4)
{
  _BYTE *v7; // rbx
  wchar_t *v8; // r8
  __int64 v9; // rax
  _BYTE *i; // rcx
  unsigned int v11; // edx
  CVarObjHeap *v12; // rcx
  unsigned int v13; // edi
  wchar_t *v14; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v18; // rax

  if ( *((_DWORD *)this + 2) )
  {
    if ( (unsigned __int64)a2 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      MemLogObject = GetMemLogObject();
      v13 = 87;
      CMemoryLog::Write(MemLogObject, 87);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, 87);
      }
      v18 = GetMemLogObject();
      CMemoryLog::Write(v18, 87);
    }
    else
    {
      if ( !CFlexArray::Size(a2) )
        return 18;
      v7 = *(_BYTE **)CFlexArray::operator[](a2, 0);
      CFlexArray::RemoveAt(a2, 0);
      v8 = (wchar_t *)*a3;
      if ( a4 )
      {
        i = v7;
      }
      else
      {
        v9 = -1;
        do
          ++v9;
        while ( v7[v9] );
        for ( i = &v7[v9 - 1]; *(i - 1) != 92; --i )
        {
          if ( i <= v7 )
            break;
        }
      }
      v11 = 0;
      if ( *i )
      {
        while ( v11 < 0x173 )
        {
          ++v11;
          *v8++ = (char)*i++;
          if ( !*i )
          {
            if ( v11 >= 0x173 )
              break;
            goto LABEL_14;
          }
        }
      }
      else
      {
LABEL_14:
        *v8 = 0;
      }
      if ( v7 )
        _BtrMemFree(v7);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, 0);
        v12 = WPP_GLOBAL_Control;
      }
      v13 = 0;
      if ( a4 )
        goto LABEL_25;
      v14 = wcschr(*a3, 0x2Eu);
      if ( v14 )
        *v14 = 0;
    }
    v12 = WPP_GLOBAL_Control;
LABEL_25:
    if ( v12 != (CVarObjHeap *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v12 + 2), 68, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, v13);
    return v13;
  }
  v16 = GetMemLogObject();
  CMemoryLog::Write(v16, 4317);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 4317);
  }
  return 4317;
}

```

## disassembly

```asm
0x180009920  push    rbx
0x180009922  push    rsi
0x180009923  push    rdi
0x180009924  push    r14
0x180009926  sub     rsp, 28h
0x18000992a  cmp     dword ptr [rcx+8], 0
0x18000992e  movzx   esi, r9b
0x180009932  mov     r14, r8
0x180009935  mov     rdi, rdx
0x180009938  jz      loc_180009A67
0x18000993e  lea     rax, [rdx-1]
0x180009942  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009946  ja      loc_180009AE8
0x18000994c  mov     rcx, rdx
0x18000994f  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180009955  test    eax, eax
0x180009957  jz      loc_180009A58
0x18000995d  xor     edx, edx
0x18000995f  mov     rcx, rdi
0x180009962  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x180009968  xor     edx, edx
0x18000996a  mov     rcx, rdi
0x18000996d  mov     rbx, [rax]
0x180009970  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x180009976  mov     r8, [r14]
0x180009979  test    sil, sil
0x18000997c  jnz     loc_180009ABC
0x180009982  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009989  nop     dword ptr [rax+00000000h]
0x180009990  inc     rax
0x180009993  cmp     byte ptr [rbx+rax], 0
0x180009997  jnz     short loc_180009990
0x180009999  lea     rcx, [rbx-1]
0x18000999d  add     rcx, rax
0x1800099a0  cmp     byte ptr [rcx-1], 5Ch ; '\'
0x1800099a4  jz      short loc_1800099B4
0x1800099a6  cmp     rcx, rbx
0x1800099a9  jbe     short loc_1800099B4
0x1800099ab  dec     rcx
0x1800099ae  cmp     byte ptr [rcx-1], 5Ch ; '\'
0x1800099b2  jnz     short loc_1800099A6
0x1800099b4  xor     edx, edx
0x1800099b6  cmp     [rcx], dl
0x1800099b8  jz      short loc_1800099DF
0x1800099ba  cmp     edx, 173h
0x1800099c0  jnb     short loc_1800099E5
0x1800099c2  movsx   eax, byte ptr [rcx]
0x1800099c5  inc     edx
0x1800099c7  mov     [r8], ax
0x1800099cb  inc     rcx
0x1800099ce  add     r8, 2
0x1800099d2  cmp     byte ptr [rcx], 0
0x1800099d5  jnz     short loc_1800099BA
0x1800099d7  cmp     edx, 173h
0x1800099dd  jnb     short loc_1800099E5
0x1800099df  xor     eax, eax
0x1800099e1  mov     [r8], ax
0x1800099e5  test    rbx, rbx
0x1800099e8  jnz     short loc_180009A4E
0x1800099ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099f1  lea     rbx, WPP_GLOBAL_Control
0x1800099f8  cmp     rcx, rbx
0x1800099fb  jz      short loc_180009A0D
0x1800099fd  test    byte ptr [rcx+1Ch], 1
0x180009a01  jz      short loc_180009A0D
0x180009a03  cmp     byte ptr [rcx+19h], 2
0x180009a07  jnb     loc_180009AC4
0x180009a0d  xor     edi, edi
0x180009a0f  test    sil, sil
0x180009a12  jnz     short loc_180009A33
0x180009a14  mov     rcx, [r14]; Str
0x180009a17  mov     edx, 2Eh ; '.'; Ch
0x180009a1c  call    cs:__imp_wcschr
0x180009a22  test    rax, rax
0x180009a25  jz      short loc_180009A2C
0x180009a27  xor     ecx, ecx
0x180009a29  mov     [rax], cx
0x180009a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a33  cmp     rcx, rbx
0x180009a36  jz      short loc_180009A42
0x180009a38  test    byte ptr [rcx+1Ch], 1
0x180009a3c  jnz     loc_180009B4B
0x180009a42  mov     eax, edi
0x180009a44  add     rsp, 28h
0x180009a48  pop     r14
0x180009a4a  pop     rdi
0x180009a4b  pop     rsi
0x180009a4c  pop     rbx
0x180009a4d  retn
0x180009a4e  mov     rcx, rbx; void *
0x180009a51  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180009a56  jmp     short loc_1800099EA
0x180009a58  mov     eax, 12h
0x180009a5d  add     rsp, 28h
0x180009a61  pop     r14
0x180009a63  pop     rdi
0x180009a64  pop     rsi
0x180009a65  pop     rbx
0x180009a66  retn
0x180009a67  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009a6d  mov     rcx, rax
0x180009a70  mov     edx, 10DDh
0x180009a75  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a82  lea     rbx, WPP_GLOBAL_Control
0x180009a89  cmp     rcx, rbx
0x180009a8c  jz      short loc_180009AB5
0x180009a8e  test    byte ptr [rcx+1Ch], 1
0x180009a92  jz      short loc_180009AB5
0x180009a94  cmp     byte ptr [rcx+19h], 2
0x180009a98  jb      short loc_180009AB5
0x180009a9a  mov     rcx, [rcx+10h]
0x180009a9e  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180009aa5  mov     edx, 43h ; 'C'
0x180009aaa  mov     r9d, 10DDh
0x180009ab0  call    WPP_SF_d
0x180009ab5  mov     eax, 10DDh
0x180009aba  jmp     short loc_180009A44
0x180009abc  mov     rcx, rbx
0x180009abf  jmp     loc_1800099B4
0x180009ac4  mov     rcx, [rcx+10h]
0x180009ac8  lea     r8, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids
0x180009acf  mov     edx, 1Fh
0x180009ad4  xor     r9d, r9d
0x180009ad7  call    WPP_SF_d
0x180009adc  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ae3  jmp     loc_180009A0D
0x180009ae8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009aee  mov     edi, 57h ; 'W'
0x180009af3  mov     rcx, rax
0x180009af6  mov     edx, edi
0x180009af8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009afe  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b05  lea     rbx, WPP_GLOBAL_Control
0x180009b0c  cmp     rcx, rbx
0x180009b0f  jz      short loc_180009B35
0x180009b11  test    byte ptr [rcx+1Ch], 1
0x180009b15  jz      short loc_180009B35
0x180009b17  cmp     byte ptr [rcx+19h], 2
0x180009b1b  jb      short loc_180009B35
0x180009b1d  mov     rcx, [rcx+10h]
0x180009b21  lea     r8, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids
0x180009b28  mov     edx, 1Eh
0x180009b2d  mov     r9d, edi
0x180009b30  call    WPP_SF_d
0x180009b35  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009b3b  mov     rcx, rax
0x180009b3e  mov     edx, edi
0x180009b40  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009b46  jmp     loc_180009A2C
0x180009b4b  cmp     byte ptr [rcx+19h], 2
0x180009b4f  jb      loc_180009A42
0x180009b55  mov     rcx, [rcx+10h]
0x180009b59  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180009b60  mov     edx, 44h ; 'D'
0x180009b65  mov     r9d, edi
0x180009b68  call    WPP_SF_d
0x180009b6d  jmp     loc_180009A42
```
