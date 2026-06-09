# InitParseTables

- ea: `0x14005edbc`
- end: `0x14006012a`
- name: `InitParseTables`
- size: `4974`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140074b48`

## string_xrefs

- `0x14005f017`: `defaultSidebearingY`
- `0x14005f3b2`: `defaultSidebearingY`
- `0x14005effc`: `defaultSidebearingX`
- `0x14005f3a4`: `defaultSidebearingX`
- `0x14005fe53`: `Registry`

## pseudocode

```c
__int64 InitParseTables()
{
  __int64 result; // rax

  dword_1400B5200 = 152;
  dword_1400B5218 = 148;
  qword_1400B51F8 = (__int64)SetBlendFixed;
  PrivateBlend = (__int64)&qword_1400B51F0;
  qword_1400B5240 = (__int64)ParseBlendBlues;
  qword_1400B7110 = (__int64)InitPrivateBlend;
  qword_1400B5270 = (__int64)ParseBlendBlues;
  qword_1400B51F0 = (__int64)"BlueFuzz";
  qword_1400B5288 = (__int64)ParseBlendOtherBlues;
  qword_1400B5248 = (__int64)&qword_1400B4158;
  qword_1400B52D0 = (__int64)ParseBlendOtherBlues;
  qword_1400B5258 = (__int64)ParseBlendErodeProc;
  qword_1400B52F8 = (__int64)"StdVW";
  qword_1400B5278 = (__int64)&qword_1400B4168;
  qword_1400B5290 = (__int64)&qword_1400B4168;
  qword_1400B5338 = (__int64)&qword_1400B4170;
  qword_1400B52A0 = (__int64)SetBlendForceBold;
  qword_1400B5208 = (__int64)"BlueScale";
  qword_1400B52D8 = (__int64)&qword_1400B4158;
  qword_1400B5210 = (__int64)SetBlendFixed;
  qword_1400B52C8 = (__int64)"OtherBlues";
  dword_1400B5230 = 156;
  qword_1400B52E0 = (__int64)"StdHW";
  qword_1400B5220 = (__int64)"BlueShift";
  qword_1400B52E8 = (__int64)ParseBlendStdW;
  qword_1400B5300 = (__int64)ParseBlendStdW;
  qword_1400B5228 = (__int64)SetBlendFixed;
  qword_1400B5320 = (__int64)&qword_1400B4160;
  qword_1400B5238 = (__int64)"BlueValues";
  qword_1400B5310 = (__int64)"StemSnapH";
  dword_1400B5260 = 20;
  qword_1400B5318 = (__int64)ParseBlendStemSnap;
  qword_1400B5330 = (__int64)ParseBlendStemSnap;
  qword_1400B5350 = (__int64)&qword_1400B4150;
  qword_1400B5340 = (__int64)"VToHOrigin";
  qword_1400B5348 = (__int64)ParseBlendVToHOrigin;
  qword_1400B5250 = (__int64)"Erode";
  qword_1400B5268 = (__int64)"FamilyBlues";
  qword_1400B5280 = (__int64)"FamilyOtherBlues";
  qword_1400B5298 = (__int64)"ForceBold";
  dword_1400B52C0 = 48;
  qword_1400B52B0 = (__int64)"HBaselineShift";
  qword_1400B52B8 = (__int64)SetBlendFixed;
  dword_1400B52F0 = 16;
  dword_1400B5308 = 20;
  qword_1400B5328 = (__int64)"StemSnapV";
  dword_1400B7108 = 20;
  qword_1400B5358 = (__int64)"defaultSidebearingX";
  qword_1400B53E8 = (__int64)"BlueScale";
  qword_1400B5370 = (__int64)"defaultSidebearingY";
  qword_1400B5418 = (__int64)"BlueValues";
  qword_1400B5388 = (__int64)"defaultWidthX";
  qword_1400B5420 = (__int64)ParseBlues;
  qword_1400B53A0 = (__int64)"defaultWidthY";
  qword_1400B5480 = (__int64)ParseBlues;
  qword_1400B53B8 = (__int64)"nominalWidthX";
  dword_1400B5368 = 24;
  Private = (__int64)&qword_1400B53D0;
  qword_1400B70D0 = (__int64)InitPrivate;
  qword_1400B53D0 = (__int64)"BlueFuzz";
  qword_1400B53D8 = (__int64)SetFixed;
  qword_1400B5430 = (__int64)"CDV";
  qword_1400B5450 = (__int64)ParseErodeProc;
  qword_1400B5460 = (__int64)"ExpansionFactor";
  qword_1400B5488 = (__int64)&qword_1400B4168;
  qword_1400B54A0 = (__int64)&qword_1400B4168;
  qword_1400B54B0 = (__int64)SetForceBold;
  qword_1400B54C0 = (__int64)"ForceBoldThreshold";
  qword_1400B54F0 = (__int64)"LanguageGroup";
  qword_1400B5508 = (__int64)"NDV";
  qword_1400B5360 = (__int64)SetBlendFixed;
  dword_1400B5380 = 28;
  qword_1400B5378 = (__int64)SetBlendFixed;
  dword_1400B5398 = 32;
  qword_1400B5390 = (__int64)SetBlendFixed;
  dword_1400B53B0 = 36;
  qword_1400B53A8 = (__int64)SetBlendFixed;
  dword_1400B53C8 = 352;
  qword_1400B53C0 = (__int64)SetBlendFixed;
  dword_1400B53E0 = 152;
  dword_1400B53F8 = 148;
  qword_1400B53F0 = (__int64)SetFixed;
  dword_1400B5410 = 156;
  qword_1400B5400 = (__int64)"BlueShift";
  qword_1400B5408 = (__int64)SetFixed;
  qword_1400B5428 = (__int64)&qword_1400B4158;
  dword_1400B5440 = 84;
  qword_1400B5438 = (__int64)SetInt16;
  qword_1400B5448 = (__int64)"Erode";
  dword_1400B5470 = -72;
  qword_1400B5468 = (__int64)SetFixed;
  qword_1400B5478 = (__int64)"FamilyBlues";
  qword_1400B5490 = (__int64)"FamilyOtherBlues";
  qword_1400B5498 = (__int64)ParseOtherBlues;
  qword_1400B54A8 = (__int64)"ForceBold";
  dword_1400B54D0 = -68;
  qword_1400B54C8 = (__int64)SetFixed;
  dword_1400B54E8 = 48;
  qword_1400B54D8 = (__int64)"HBaselineShift";
  qword_1400B54E0 = (__int64)SetFixed;
  dword_1400B5500 = 70;
  qword_1400B54F8 = (__int64)SetInt16;
  dword_1400B5518 = 82;
  qword_1400B5510 = (__int64)SetInt16;
  qword_1400B5530 = (__int64)&qword_1400B4158;
  qword_1400B5528 = (__int64)ParseOtherBlues;
  dword_1400B5548 = 456;
  qword_1400B5520 = (__int64)"OtherBlues";
  qword_1400B55A8 = (__int64)&qword_1400B4160;
  qword_1400B5538 = (__int64)"PGFontID";
  qword_1400B55C0 = (__int64)&qword_1400B4170;
  qword_1400B5550 = (__int64)"RndStemUp";
  qword_1400B55D8 = (__int64)&qword_1400B4160;
  qword_1400B5558 = (__int64)SetRndStemUp;
  qword_1400B55F0 = (__int64)&qword_1400B4170;
  qword_1400B5568 = (__int64)"RunInt";
  qword_1400B5540 = (__int64)CallIntProc;
  qword_1400B5580 = (__int64)"SDBytes";
  dword_1400B5578 = 464;
  qword_1400B5598 = (__int64)"StdHW";
  qword_1400B55A0 = (__int64)ParseStdW;
  qword_1400B55B8 = (__int64)ParseStdW;
  qword_1400B55C8 = (__int64)"StemSnapH";
  qword_1400B55E0 = (__int64)"StemSnapV";
  qword_1400B55F8 = (__int64)"SubrCount";
  qword_1400B5610 = (__int64)"SubrMapOffset";
  qword_1400B5628 = (__int64)"UniqueID";
  qword_1400B5630 = (__int64)SetInt32;
  qword_1400B5650 = (__int64)&qword_1400B4150;
  qword_1400B5640 = (__int64)"VToHOrigin";
  qword_1400B5658 = (__int64)"defaultSidebearingX";
  qword_1400B5670 = (__int64)"defaultSidebearingY";
  qword_1400B5688 = (__int64)"defaultWidthX";
  qword_1400B56A0 = (__int64)"defaultWidthY";
  qword_1400B56B8 = (__int64)"gSubNumberBias";
  qword_1400B5570 = (__int64)CallStringProc;
  dword_1400B5590 = 600;
  qword_1400B5588 = (__int64)CallIntProc;
  qword_1400B55B0 = (__int64)"StdVW";
  qword_1400B55D0 = (__int64)SetFixedArray;
  qword_1400B55E8 = (__int64)SetFixedArray;
  dword_1400B5608 = 616;
  qword_1400B5600 = (__int64)CallIntProc;
  dword_1400B5620 = 608;
  qword_1400B5618 = (__int64)CallIntProc;
  dword_1400B5638 = 28;
  qword_1400B5648 = (__int64)SetFixedArray;
  dword_1400B5668 = 24;
  qword_1400B5660 = (__int64)SetFixed;
  dword_1400B5680 = 28;
  qword_1400B5678 = (__int64)SetFixed;
  dword_1400B5698 = 32;
  qword_1400B5690 = (__int64)SetFixed;
  dword_1400B56B0 = 36;
  qword_1400B56A8 = (__int64)SetFixed;
  dword_1400B56C8 = 78;
  qword_1400B56C0 = (__int64)SetInt16;
  dword_1400B56E0 = -64;
  qword_1400B56D8 = (__int64)SetFixed;
  qword_1400B56D0 = (__int64)"initialRandomSeed";
  qword_1400B5720 = (__int64)SetFixed;
  qword_1400B56E8 = (__int64)"lenBuildCharArray";
  qword_1400B5778 = (__int64)"UnderlinePosition";
  qword_1400B5700 = (__int64)"lenIV";
  dword_1400B56F8 = 80;
  qword_1400B5718 = (__int64)"nominalWidthX";
  qword_1400B56F0 = (__int64)SetInt16;
  qword_1400B5730 = (__int64)"subroutineNumberBias";
  dword_1400B5710 = 56;
  BlendDict = (__int64)&qword_1400B5748;
  qword_1400B5708 = (__int64)SetInt16;
  qword_1400B70F0 = (__int64)InitBlendDict;
  dword_1400B5728 = 352;
  qword_1400B5750 = (__int64)SetBlendFontBBox;
  dword_1400B5740 = 76;
  qword_1400B5768 = (__int64)CallBlendFixedProc;
  qword_1400B5780 = (__int64)CallBlendFixedProc;
  qword_1400B5798 = (__int64)CallBlendFixedProc;
  qword_1400B5738 = (__int64)SetInt16;
  FontDict = (__int64)&qword_1400B57A8;
  dword_1400B70C8 = 37;
  qword_1400B57B8 = (__int64)&accentEncoding;
  qword_1400B57A8 = (__int64)"AccentEncoding";
  qword_1400B57C0 = (__int64)"BlendAxisTypes";
  qword_1400B57C8 = (__int64)SetBlendAxisTypes;
  qword_1400B57D8 = (__int64)"BlendDesignMap";
  qword_1400B57E0 = (__int64)SetBlendDesignMap;
  qword_1400B57F0 = (__int64)"BlendDesignPositions";
  qword_1400B57F8 = (__int64)SetBlendDesignPositions;
  qword_1400B5850 = (__int64)"FamilyName";
  qword_1400B5748 = (__int64)"FontBBox";
  dword_1400B5770 = 280;
  qword_1400B5760 = (__int64)"ItalicAngle";
  dword_1400B5788 = 264;
  dword_1400B57A0 = 272;
  qword_1400B5790 = (__int64)"UnderlineThickness";
  dword_1400B70E8 = 4;
  qword_1400B7130 = 0;
  qword_1400B57B0 = (__int64)DoEncoding;
  qword_1400B5808 = (__int64)"CDevProc";
  qword_1400B5810 = (__int64)SetCDevProc;
  qword_1400B5820 = (__int64)"CharOffsets";
  qword_1400B5828 = (__int64)SetCharOffsets;
  qword_1400B5848 = (__int64)&encoding;
  qword_1400B5838 = (__int64)"Encoding";
  qword_1400B5840 = (__int64)DoEncoding;
  dword_1400B5860 = 96;
  qword_1400B5858 = (__int64)CallStringProc;
  qword_1400B5868 = (__int64)"FontBBox";
  qword_1400B5870 = (__int64)SetFontBBox;
  qword_1400B58A0 = (__int64)CallStringProc;
  qword_1400B5880 = (__int64)"FontMatrix";
  qword_1400B58B8 = (__int64)SetFontType;
  qword_1400B5888 = (__int64)SetFontMatrix;
  qword_1400B58D0 = (__int64)CallStringProc;
  qword_1400B5898 = (__int64)"FontName";
  qword_1400B58E0 = (__int64)"ItalicAngle";
  qword_1400B58B0 = (__int64)"FontType";
  dword_1400B5908 = 80;
  qword_1400B58C8 = (__int64)"FullName";
  qword_1400B5900 = (__int64)CallStringProc;
  qword_1400B58F8 = (__int64)"Notice";
  qword_1400B5930 = (__int64)SetFontType;
  qword_1400B5928 = (__int64)"PGFontType";
  dword_1400B58A8 = 72;
  qword_1400B5948 = (__int64)SetInt16;
  qword_1400B5958 = (__int64)"PrimogenitalFontName";
  qword_1400B5960 = (__int64)CallStringProc;
  qword_1400B5970 = (__int64)"StrokeWidth";
  qword_1400B5978 = (__int64)SetFixed;
  qword_1400B59A0 = (__int64)"UnderlinePosition";
  qword_1400B59B8 = (__int64)"UnderlineThickness";
  qword_1400B59D0 = (__int64)"UniqueID";
  qword_1400B59D8 = (__int64)CallIntProc;
  qword_1400B59E8 = (__int64)"Weight";
  qword_1400B59F0 = (__int64)CallStringProc;
  qword_1400B5A00 = (__int64)"WeightVector";
  qword_1400B5A08 = (__int64)SetWeightVector;
  qword_1400B5A18 = (__int64)"isFixedPitch";
  qword_1400B5A20 = (__int64)CallBooleanProc;
  dword_1400B58D8 = 88;
  dword_1400B58F0 = 120;
  qword_1400B58E8 = (__int64)CallFixedProc;
  qword_1400B5910 = (__int64)"PGFArray";
  qword_1400B5918 = (__int64)SetPGFArray;
  dword_1400B5950 = 60;
  qword_1400B5940 = (__int64)"PaintType";
  dword_1400B5968 = 72;
  dword_1400B5980 = -76;
  qword_1400B5988 = (__int64)"SubsVector";
  qword_1400B5990 = (__int64)SetSubsVector;
  dword_1400B59B0 = 136;
  qword_1400B59A8 = (__int64)CallFixedProc;
  dword_1400B59C8 = 144;
  qword_1400B59C0 = (__int64)CallFixedProc;
  dword_1400B59E0 = 152;
  dword_1400B59F8 = 104;
  dword_1400B5A28 = 128;
  qword_1400B5B70 = (__int64)SetSubsVector;
  qword_1400B5A38 = (__int64)SetVersion;
  qword_1400B5B38 = (__int64)"PaintType";
  CompositeDict = (__int64)&qword_1400B5A48;
  qword_1400B5B68 = (__int64)"SubsVector";
  qword_1400B5A60 = (__int64)"FDepVector";
  qword_1400B5B88 = (__int64)CallIntProc;
  qword_1400B5A68 = (__int64)SetFDepVector;
  qword_1400B5A30 = (__int64)"version";
  qword_1400B5A78 = (__int64)"FMapType";
  dword_1400B7128 = 28;
  qword_1400B5A80 = (__int64)CallIntProc;
  qword_1400B5A90 = (__int64)"FontBBox";
  qword_1400B5A98 = (__int64)SetFontBBox;
  qword_1400B5AA8 = (__int64)"FontMatrix";
  qword_1400B5AB0 = (__int64)SetFontMatrix;
  qword_1400B5AC0 = (__int64)"FontName";
  qword_1400B5AC8 = (__int64)CallStringProc;
  qword_1400B5AD8 = (__int64)"FontType";
  qword_1400B5AE0 = (__int64)SetFontType;
  qword_1400B5AF0 = (__int64)"MDFV";
  qword_1400B5AF8 = (__int64)SetMDFV;
  qword_1400B5B08 = (__int64)"MDID";
  qword_1400B5B10 = (__int64)CallIntProc;
  qword_1400B5B20 = (__int64)"PGFontID";
  qword_1400B5B28 = (__int64)CallIntProc;
  qword_1400B5B40 = (__int64)SetInt16;
  qword_1400B5B50 = (__int64)"PrefEnc";
  qword_1400B5B58 = (__int64)CallStringProc;
  qword_1400B5BA0 = (__int64)CallStringProc;
  DerivedDict = (__int64)&qword_1400B5BB0;
  qword_1400B71F0 = 0;
  qword_1400B5A58 = (__int64)&encoding;
  qword_1400B5A48 = (__int64)"Encoding";
  qword_1400B5A50 = (__int64)DoEncoding;
  dword_1400B5A88 = 320;
  dword_1400B5AD0 = 72;
  dword_1400B5B18 = 408;
  dword_1400B5B30 = 456;
  dword_1400B5B48 = 60;
  dword_1400B5B60 = 392;
  dword_1400B5B90 = 296;
  qword_1400B5B80 = (__int64)"WMode";
  dword_1400B5BA8 = 112;
  qword_1400B5B98 = (__int64)"version";
  dword_1400B71E8 = 15;
  qword_1400B7190 = 0;
  qword_1400B5BB0 = (__int64)"CDevProc";
  qword_1400B5BB8 = (__int64)SetCDevProc;
  qword_1400B5BC8 = (__int64)"CharOffsets";
  qword_1400B5BD0 = (__int64)SetCharOffsets;
  dword_1400B5BF0 = 384;
  qword_1400B5C08 = (__int64)&encoding;
  qword_1400B5BE0 = (__int64)"CharStrings";
  qword_1400B5BE8 = (__int64)CallStringProc;
  qword_1400B5C10 = (__int64)"FontBBox";
  qword_1400B5BF8 = (__int64)"Encoding";
  qword_1400B5C18 = (__int64)SetFontBBox;
  qword_1400B5C00 = (__int64)DoEncoding;
  qword_1400B5C90 = (__int64)SetInt16;
  dword_1400B5C50 = 72;
  qword_1400B5CA0 = (__int64)"UniqueID";
  qword_1400B5C48 = (__int64)CallStringProc;
  qword_1400B5CD8 = (__int64)CallStringProc;
  qword_1400B5C78 = (__int64)SetPGFArray;
  CIDFontDict = (__int64)&qword_1400B5CE8;
  dword_1400B5D10 = 72;
  qword_1400B5CE8 = (__int64)"CIDCount";
  qword_1400B5C28 = (__int64)"FontMatrix";
  qword_1400B5D00 = (__int64)"CIDFontName";
  qword_1400B5C30 = (__int64)SetFontMatrix;
  qword_1400B5D18 = (__int64)"CIDFontType";
  qword_1400B5C40 = (__int64)"FontName";
  qword_1400B5D30 = (__int64)"CIDFontVersion";
  qword_1400B5D48 = (__int64)"CIDMapOffset";
  qword_1400B5D60 = (__int64)"FDArray";
  qword_1400B5D68 = (__int64)SetFontDictArray;
  qword_1400B5D78 = (__int64)"FDBytes";
  qword_1400B5D90 = (__int64)"FontBBox";
  qword_1400B5D98 = (__int64)SetFontBBox;
  qword_1400B5C58 = (__int64)"FontType";
  qword_1400B5C60 = (__int64)SetFontType;
  qword_1400B5C70 = (__int64)"PGFArray";
  dword_1400B5C98 = 60;
  qword_1400B5C88 = (__int64)"PaintType";
  dword_1400B5CB0 = 152;
  qword_1400B5CA8 = (__int64)CallIntProc;
  dword_1400B5CC8 = 296;
  qword_1400B5CB8 = (__int64)"WMode";
  qword_1400B5CC0 = (__int64)CallIntProc;
  dword_1400B5CE0 = 112;
  qword_1400B5CD0 = (__int64)"version";
  dword_1400B7188 = 13;
  qword_1400B7150 = 0;
  dword_1400B5CF8 = 496;
  qword_1400B5CF0 = (__int64)CallIntProc;
  qword_1400B5D08 = (__int64)CallStringProc;
  qword_1400B5D20 = (__int64)SetFontType;
  dword_1400B5D40 = 512;
  qword_1400B5D38 = (__int64)CallIntProc;
  dword_1400B5D58 = 504;
  qword_1400B5D50 = (__int64)CallIntProc;
  dword_1400B5D88 = 488;
  qword_1400B5D80 = (__int64)CallIntProc;
  qword_1400B5DA8 = (__int64)"FontMatrix";
  qword_1400B5DB0 = (__int64)SetFontMatrix;
  qword_1400B5E10 = (__int64)CallIntProc;
  dword_1400B5E78 = 60;
  qword_1400B5DF0 = (__int64)"FullName";
  qword_1400B5E68 = (__int64)"PaintType";
  qword_1400B5E08 = (__int64)"GDBytes";
  dword_1400B5DD0 = 544;
  qword_1400B5E20 = (__int64)"HostSupport";
  qword_1400B5DC0 = (__int64)"FontName";
  qword_1400B5E38 = (__int64)"Notice";
  qword_1400B5DC8 = (__int64)CallStringProc;
  qword_1400B5E70 = (__int64)SetInt32;
  qword_1400B5DD8 = (__int64)"FontType";
  qword_1400B5EB0 = (__int64)"UIDBase";
  qword_1400B5DE0 = (__int64)SetFontType;
  qword_1400B5EC8 = (__int64)"UnderlinePosition";
  dword_1400B5E00 = 88;
  qword_1400B5ED0 = (__int64)CallFixedProc;
  qword_1400B5EE8 = (__int64)CallFixedProc;
  qword_1400B5EF8 = (__int64)"XUID";
  qword_1400B5F00 = (__int64)DoXUID;
  EncodingDict = (__int64)&qword_1400B5F10;
  qword_1400B5F58 = (__int64)"beginbfchar";
  qword_1400B5F60 = (__int64)DoBFChar;
  qword_1400B5F70 = (__int64)"beginbfrange";
  qword_1400B5F78 = (__int64)DoBFRange;
  qword_1400B5F88 = (__int64)"begincidchar";
  qword_1400B5DF8 = (__int64)CallStringProc;
  dword_1400B5E18 = 480;
  dword_1400B5E30 = 744;
  qword_1400B5E28 = (__int64)CallStringProc;
  dword_1400B5E48 = 80;
  qword_1400B5E40 = (__int64)CallStringProc;
  dword_1400B5E60 = 528;
  qword_1400B5E50 = (__int64)"Ordering";
  qword_1400B5E58 = (__int64)CallStringProc;
  dword_1400B5E90 = 520;
  qword_1400B5E80 = (__int64)"Registry";
  qword_1400B5E88 = (__int64)CallStringProc;
  dword_1400B5EA8 = 536;
  qword_1400B5E98 = (__int64)"Supplement";
  qword_1400B5EA0 = (__int64)CallIntProc;
  dword_1400B5EC0 = 584;
  qword_1400B5EB8 = (__int64)CallIntProc;
  dword_1400B5ED8 = 136;
  dword_1400B5EF0 = 144;
  qword_1400B5EE0 = (__int64)"UnderlineThickness";
  dword_1400B7148 = 23;
  qword_1400B7030 = 0;
  dword_1400B5F20 = 528;
  qword_1400B5F10 = (__int64)"Ordering";
  qword_1400B5F18 = (__int64)CallStringProc;
  dword_1400B5F38 = 520;
  qword_1400B5F28 = (__int64)"Registry";
  qword_1400B5F30 = (__int64)CallStringProc;
  dword_1400B5F50 = 536;
  qword_1400B5F40 = (__int64)"Supplement";
  qword_1400B5F48 = (__int64)CallIntProc;
  dword_1400B7028 = 14;
  qword_1400B5F90 = (__int64)DoCIDChar;
  qword_1400B5FA8 = (__int64)DoCIDRange;
  qword_1400B5FA0 = (__int64)"begincidrange";
  qword_1400B5FB8 = (__int64)"begincodespacerange";
  qword_1400B5FC0 = (__int64)DoCodeSpaceRange;
  qword_1400B5FD0 = (__int64)"beginnotdefchar";
  qword_1400B5FD8 = (__int64)DoNotDefChar;
  qword_1400B5FE8 = (__int64)"beginnotdefrange";
  qword_1400B5FF0 = (__int64)DoNotDefRange;
  qword_1400B6000 = (__int64)"beginpgfrange";
  qword_1400B6018 = (__int64)"beginusematrix";
  qword_1400B6020 = (__int64)DoUseMatrix;
  qword_1400B6030 = (__int64)"usecmap";
  qword_1400B6038 = (__int64)DoUseCMap;
  qword_1400B6048 = (__int64)"usefont";
  qword_1400B6050 = (__int64)DoUseFont;
  result = 0;
  qword_1400B6008 = (__int64)DoCIDRange;
  return result;
}

```

## disassembly

```asm
0x14005edbc  push    rbx
0x14005edbe  push    rbp
0x14005edbf  push    rsi
0x14005edc0  push    rdi
0x14005edc1  push    r12
0x14005edc3  push    r13
0x14005edc5  push    r14
0x14005edc7  push    r15
0x14005edc9  mov     r12d, 94h
0x14005edcf  mov     cs:dword_1400B5200, 98h
0x14005edd9  lea     r8, SetBlendFixed
0x14005ede0  mov     cs:dword_1400B5218, r12d
0x14005ede7  lea     rax, qword_1400B51F0
0x14005edee  mov     cs:qword_1400B51F8, r8
0x14005edf5  mov     cs:PrivateBlend, rax
0x14005edfc  lea     rcx, ParseBlendBlues
0x14005ee03  mov     cs:qword_1400B5240, rcx
0x14005ee0a  lea     rax, InitPrivateBlend
0x14005ee11  mov     cs:qword_1400B7110, rax
0x14005ee18  lea     edx, [r12-80h]
0x14005ee1d  mov     cs:qword_1400B5270, rcx
0x14005ee24  lea     rax, aBluefuzz; "BlueFuzz"
0x14005ee2b  mov     cs:qword_1400B51F0, rax
0x14005ee32  lea     rcx, ParseBlendOtherBlues
0x14005ee39  lea     rax, qword_1400B4158
0x14005ee40  mov     cs:qword_1400B5288, rcx
0x14005ee47  mov     cs:qword_1400B5248, rax
0x14005ee4e  lea     rbp, aBluescale; "BlueScale"
0x14005ee55  mov     cs:qword_1400B52D0, rcx
0x14005ee5c  lea     rax, ParseBlendErodeProc
0x14005ee63  mov     cs:qword_1400B5258, rax
0x14005ee6a  lea     rcx, aStdvw; "StdVW"
0x14005ee71  lea     rax, qword_1400B4168
0x14005ee78  mov     cs:qword_1400B52F8, rcx
0x14005ee7f  mov     cs:qword_1400B5278, rax
0x14005ee86  lea     rcx, qword_1400B4170
0x14005ee8d  mov     cs:qword_1400B5290, rax
0x14005ee94  lea     edi, [r12+8]
0x14005ee99  lea     rax, SetBlendForceBold
0x14005eea0  mov     cs:qword_1400B5338, rcx
0x14005eea7  mov     cs:qword_1400B52A0, rax
0x14005eeae  lea     r10, aBlueshift; "BlueShift"
0x14005eeb5  lea     rax, qword_1400B4158
0x14005eebc  mov     cs:qword_1400B5208, rbp
0x14005eec3  mov     cs:qword_1400B52D8, rax
0x14005eeca  lea     r9, aBluevalues; "BlueValues"
0x14005eed1  lea     rax, aOtherblues; "OtherBlues"
0x14005eed8  mov     cs:qword_1400B5210, r8
0x14005eedf  mov     cs:qword_1400B52C8, rax
0x14005eee6  lea     r11, aErode; "Erode"
0x14005eeed  lea     rax, aStdhw; "StdHW"
0x14005eef4  mov     cs:dword_1400B5230, edi
0x14005eefa  mov     cs:qword_1400B52E0, rax
0x14005ef01  lea     r14, aFamilyblues; "FamilyBlues"
0x14005ef08  lea     rax, ParseBlendStdW
0x14005ef0f  mov     cs:qword_1400B5220, r10
0x14005ef16  mov     cs:qword_1400B52E8, rax
0x14005ef1d  lea     rsi, aFamilyotherblu; "FamilyOtherBlues"
0x14005ef24  mov     cs:qword_1400B5300, rax
0x14005ef2b  lea     rbx, aForcebold; "ForceBold"
0x14005ef32  lea     rax, qword_1400B4160
0x14005ef39  mov     cs:qword_1400B5228, r8
0x14005ef40  mov     cs:qword_1400B5320, rax
0x14005ef47  lea     r13d, [r12-64h]
0x14005ef4c  lea     rax, aStemsnaph; "StemSnapH"
0x14005ef53  mov     cs:qword_1400B5238, r9
0x14005ef5a  mov     cs:qword_1400B5310, rax
0x14005ef61  lea     r15, aHbaselineshift; "HBaselineShift"
0x14005ef68  lea     rax, ParseBlendStemSnap
0x14005ef6f  mov     cs:dword_1400B5260, edx
0x14005ef75  mov     cs:qword_1400B5318, rax
0x14005ef7c  lea     rcx, aStemsnapv; "StemSnapV"
0x14005ef83  mov     cs:qword_1400B5330, rax
0x14005ef8a  lea     rax, qword_1400B4150
0x14005ef91  mov     cs:qword_1400B5350, rax
0x14005ef98  lea     rax, aVtohorigin; "VToHOrigin"
0x14005ef9f  mov     cs:qword_1400B5340, rax
0x14005efa6  lea     rax, ParseBlendVToHOrigin
0x14005efad  mov     cs:qword_1400B5348, rax
0x14005efb4  mov     cs:qword_1400B5250, r11
0x14005efbb  mov     cs:qword_1400B5268, r14
0x14005efc2  mov     cs:qword_1400B5280, rsi
0x14005efc9  mov     cs:qword_1400B5298, rbx
0x14005efd0  mov     cs:dword_1400B52C0, r13d
0x14005efd7  mov     cs:qword_1400B52B0, r15
0x14005efde  mov     cs:qword_1400B52B8, r8
0x14005efe5  mov     cs:dword_1400B52F0, 10h
0x14005efef  mov     cs:dword_1400B5308, edx
0x14005eff5  mov     cs:qword_1400B5328, rcx
0x14005effc  lea     rax, aDefaultsidebea_0; "defaultSidebearingX"
0x14005f003  mov     cs:dword_1400B7108, edx
0x14005f009  mov     cs:qword_1400B5358, rax
0x14005f010  lea     rcx, ParseBlues
0x14005f017  lea     rax, aDefaultsidebea; "defaultSidebearingY"
0x14005f01e  mov     cs:qword_1400B53E8, rbp
0x14005f025  mov     cs:qword_1400B5370, rax
0x14005f02c  lea     rbp, SetFixed
0x14005f033  lea     rax, aDefaultwidthx; "defaultWidthX"
0x14005f03a  mov     cs:qword_1400B5418, r9
0x14005f041  mov     cs:qword_1400B5388, rax
0x14005f048  lea     r9, SetInt16
0x14005f04f  lea     rax, aDefaultwidthy; "defaultWidthY"
0x14005f056  mov     cs:qword_1400B5420, rcx
0x14005f05d  mov     cs:qword_1400B53A0, rax
0x14005f064  lea     rdx, qword_1400B4158
0x14005f06b  lea     rax, aNominalwidthx; "nominalWidthX"
0x14005f072  mov     cs:qword_1400B5480, rcx
0x14005f079  mov     cs:qword_1400B53B8, rax
0x14005f080  lea     rcx, ParseOtherBlues
0x14005f087  lea     rax, qword_1400B53D0
0x14005f08e  mov     cs:dword_1400B5368, 18h
0x14005f098  mov     cs:Private, rax
0x14005f09f  lea     rax, InitPrivate
0x14005f0a6  mov     cs:qword_1400B70D0, rax
0x14005f0ad  lea     rax, aBluefuzz; "BlueFuzz"
0x14005f0b4  mov     cs:qword_1400B53D0, rax
0x14005f0bb  lea     rax, SetFixed
0x14005f0c2  mov     cs:qword_1400B53D8, rax
0x14005f0c9  lea     rax, aCdv; "CDV"
0x14005f0d0  mov     cs:qword_1400B5430, rax
0x14005f0d7  lea     rax, ParseErodeProc
0x14005f0de  mov     cs:qword_1400B5450, rax
0x14005f0e5  lea     rax, aExpansionfacto; "ExpansionFactor"
0x14005f0ec  mov     cs:qword_1400B5460, rax
0x14005f0f3  lea     rax, qword_1400B4168
0x14005f0fa  mov     cs:qword_1400B5488, rax
0x14005f101  mov     cs:qword_1400B54A0, rax
0x14005f108  lea     rax, SetForceBold
0x14005f10f  mov     cs:qword_1400B54B0, rax
0x14005f116  lea     rax, aForceboldthres; "ForceBoldThreshold"
0x14005f11d  mov     cs:qword_1400B54C0, rax
0x14005f124  lea     rax, aLanguagegroup; "LanguageGroup"
0x14005f12b  mov     cs:qword_1400B54F0, rax
0x14005f132  lea     rax, aNdv; "NDV"
0x14005f139  mov     cs:qword_1400B5508, rax
0x14005f140  mov     cs:qword_1400B5360, r8
0x14005f147  mov     cs:dword_1400B5380, 1Ch
0x14005f151  mov     cs:qword_1400B5378, r8
0x14005f158  mov     cs:dword_1400B5398, 20h ; ' '
0x14005f162  mov     cs:qword_1400B5390, r8
0x14005f169  mov     cs:dword_1400B53B0, 24h ; '$'
0x14005f173  mov     cs:qword_1400B53A8, r8
0x14005f17a  mov     cs:dword_1400B53C8, 160h
0x14005f184  mov     cs:qword_1400B53C0, r8
0x14005f18b  mov     cs:dword_1400B53E0, 98h
0x14005f195  mov     cs:dword_1400B53F8, r12d
0x14005f19c  mov     cs:qword_1400B53F0, rbp
0x14005f1a3  mov     cs:dword_1400B5410, edi
0x14005f1a9  mov     cs:qword_1400B5400, r10
0x14005f1b0  mov     cs:qword_1400B5408, rbp
0x14005f1b7  mov     cs:qword_1400B5428, rdx
0x14005f1be  mov     cs:dword_1400B5440, 54h ; 'T'
0x14005f1c8  mov     cs:qword_1400B5438, r9
0x14005f1cf  mov     cs:qword_1400B5448, r11
0x14005f1d6  mov     cs:dword_1400B5470, 0FFFFFFB8h
0x14005f1e0  mov     cs:qword_1400B5468, rbp
0x14005f1e7  mov     cs:qword_1400B5478, r14
0x14005f1ee  mov     cs:qword_1400B5490, rsi
0x14005f1f5  mov     cs:qword_1400B5498, rcx
0x14005f1fc  mov     cs:qword_1400B54A8, rbx
0x14005f203  mov     cs:dword_1400B54D0, 0FFFFFFBCh
0x14005f20d  mov     cs:qword_1400B54C8, rbp
0x14005f214  mov     cs:dword_1400B54E8, r13d
0x14005f21b  mov     cs:qword_1400B54D8, r15
0x14005f222  mov     cs:qword_1400B54E0, rbp
0x14005f229  mov     cs:dword_1400B5500, 46h ; 'F'
0x14005f233  mov     cs:qword_1400B54F8, r9
0x14005f23a  mov     cs:dword_1400B5518, 52h ; 'R'
0x14005f244  mov     cs:qword_1400B5510, r9
0x14005f24b  mov     cs:qword_1400B5530, rdx
0x14005f252  lea     r10, CallIntProc
0x14005f259  mov     cs:qword_1400B5528, rcx
0x14005f260  lea     rax, aOtherblues; "OtherBlues"
0x14005f267  mov     cs:dword_1400B5548, 1C8h
0x14005f271  mov     cs:qword_1400B5520, rax
0x14005f278  lea     rcx, qword_1400B4160
0x14005f27f  lea     rax, aPgfontid; "PGFontID"
0x14005f286  mov     cs:qword_1400B55A8, rcx
0x14005f28d  mov     cs:qword_1400B5538, rax
0x14005f294  lea     rdx, qword_1400B4170
0x14005f29b  lea     rax, aRndstemup; "RndStemUp"
0x14005f2a2  mov     cs:qword_1400B55C0, rdx
0x14005f2a9  mov     cs:qword_1400B5550, rax
0x14005f2b0  lea     r11, CallStringProc
0x14005f2b7  lea     rax, SetRndStemUp
0x14005f2be  mov     cs:qword_1400B55D8, rcx
0x14005f2c5  mov     cs:qword_1400B5558, rax
0x14005f2cc  lea     rcx, SetFixedArray
0x14005f2d3  lea     rax, aRunint; "RunInt"
0x14005f2da  mov     cs:qword_1400B55F0, rdx
0x14005f2e1  mov     cs:qword_1400B5568, rax
0x14005f2e8  lea     edx, [rdi-80h]
0x14005f2eb  lea     rax, aSdbytes; "SDBytes"
0x14005f2f2  mov     cs:qword_1400B5540, r10
0x14005f2f9  mov     cs:qword_1400B5580, rax
0x14005f300  lea     r8, aStdvw; "StdVW"
0x14005f307  lea     rax, aStdhw; "StdHW"
0x14005f30e  mov     cs:dword_1400B5578, 1D0h
0x14005f318  mov     cs:qword_1400B5598, rax
0x14005f31f  lea     rax, ParseStdW
0x14005f326  mov     cs:qword_1400B55A0, rax
0x14005f32d  mov     cs:qword_1400B55B8, rax
0x14005f334  lea     rax, aStemsnaph; "StemSnapH"
0x14005f33b  mov     cs:qword_1400B55C8, rax
0x14005f342  lea     rax, aStemsnapv; "StemSnapV"
0x14005f349  mov     cs:qword_1400B55E0, rax
0x14005f350  lea     rax, aSubrcount; "SubrCount"
0x14005f357  mov     cs:qword_1400B55F8, rax
0x14005f35e  lea     rax, aSubrmapoffset; "SubrMapOffset"
0x14005f365  mov     cs:qword_1400B5610, rax
0x14005f36c  lea     rax, aUniqueid; "UniqueID"
0x14005f373  mov     cs:qword_1400B5628, rax
0x14005f37a  lea     rax, SetInt32
0x14005f381  mov     cs:qword_1400B5630, rax
0x14005f388  lea     rax, qword_1400B4150
0x14005f38f  mov     cs:qword_1400B5650, rax
0x14005f396  lea     rax, aVtohorigin; "VToHOrigin"
0x14005f39d  mov     cs:qword_1400B5640, rax
0x14005f3a4  lea     rax, aDefaultsidebea_0; "defaultSidebearingX"
0x14005f3ab  mov     cs:qword_1400B5658, rax
0x14005f3b2  lea     rax, aDefaultsidebea; "defaultSidebearingY"
0x14005f3b9  mov     cs:qword_1400B5670, rax
0x14005f3c0  lea     rax, aDefaultwidthx; "defaultWidthX"
0x14005f3c7  mov     cs:qword_1400B5688, rax
0x14005f3ce  lea     rax, aDefaultwidthy; "defaultWidthY"
0x14005f3d5  mov     cs:qword_1400B56A0, rax
0x14005f3dc  lea     rax, aGsubnumberbias; "gSubNumberBias"
0x14005f3e3  mov     cs:qword_1400B56B8, rax
0x14005f3ea  mov     cs:qword_1400B5570, r11
0x14005f3f1  mov     cs:dword_1400B5590, 258h
0x14005f3fb  mov     cs:qword_1400B5588, r10
0x14005f402  mov     cs:qword_1400B55B0, r8
0x14005f409  mov     cs:qword_1400B55D0, rcx
0x14005f410  mov     cs:qword_1400B55E8, rcx
0x14005f417  mov     cs:dword_1400B5608, 268h
0x14005f421  mov     cs:qword_1400B5600, r10
0x14005f428  mov     cs:dword_1400B5620, 260h
0x14005f432  mov     cs:qword_1400B5618, r10
0x14005f439  mov     cs:dword_1400B5638, edx
0x14005f43f  mov     cs:qword_1400B5648, rcx
0x14005f446  mov     cs:dword_1400B5668, 18h
0x14005f450  mov     cs:qword_1400B5660, rbp
0x14005f457  mov     cs:dword_1400B5680, edx
0x14005f45d  mov     cs:qword_1400B5678, rbp
0x14005f464  mov     cs:dword_1400B5698, 20h ; ' '
0x14005f46e  mov     cs:qword_1400B5690, rbp
0x14005f475  mov     cs:dword_1400B56B0, 24h ; '$'
0x14005f47f  mov     cs:qword_1400B56A8, rbp
0x14005f486  mov     cs:dword_1400B56C8, 4Eh ; 'N'
0x14005f490  mov     cs:qword_1400B56C0, r9
0x14005f497  mov     cs:dword_1400B56E0, 0FFFFFFC0h
0x14005f4a1  lea     rax, aInitialrandoms; "initialRandomSeed"
0x14005f4a8  mov     cs:qword_1400B56D8, rbp
0x14005f4af  mov     cs:qword_1400B56D0, rax
0x14005f4b6  lea     r8, aUnderlineposit; "UnderlinePosition"
0x14005f4bd  lea     rax, aLenbuildcharar; "lenBuildCharArray"
0x14005f4c4  mov     cs:qword_1400B5720, rbp
0x14005f4cb  mov     cs:qword_1400B56E8, rax
0x14005f4d2  lea     r13, DoEncoding
0x14005f4d9  lea     rax, aLeniv; "lenIV"
0x14005f4e0  mov     cs:qword_1400B5778, r8
0x14005f4e7  mov     cs:qword_1400B5700, rax
0x14005f4ee  lea     r10d, [r12-44h]
0x14005f4f3  lea     rax, aNominalwidthx; "nominalWidthX"
0x14005f4fa  mov     cs:dword_1400B56F8, r10d
0x14005f501  mov     cs:qword_1400B5718, rax
0x14005f508  lea     rdx, aFontbbox; "FontBBox"
0x14005f50f  lea     rax, aSubroutinenumb; "subroutineNumberBias"
0x14005f516  mov     cs:qword_1400B56F0, r9
0x14005f51d  mov     cs:qword_1400B5730, rax
0x14005f524  lea     rcx, aItalicangle; "ItalicAngle"
0x14005f52b  lea     rax, qword_1400B5748
0x14005f532  mov     cs:dword_1400B5710, 38h ; '8'
0x14005f53c  mov     cs:BlendDict, rax
0x14005f543  lea     r8, aUnderlinethick; "UnderlineThickness"
0x14005f54a  lea     rax, InitBlendDict
0x14005f551  mov     cs:qword_1400B5708, r9
0x14005f558  mov     cs:qword_1400B70F0, rax
0x14005f55f  lea     r14, aCdevproc; "CDevProc"
0x14005f566  lea     rax, SetBlendFontBBox
0x14005f56d  mov     cs:dword_1400B5728, 160h
0x14005f577  mov     cs:qword_1400B5750, rax
0x14005f57e  lea     rsi, SetCDevProc
0x14005f585  lea     rax, CallBlendFixedProc
0x14005f58c  mov     cs:dword_1400B5740, 4Ch ; 'L'
0x14005f596  mov     cs:qword_1400B5768, rax
0x14005f59d  lea     rdi, aCharoffsets; "CharOffsets"
0x14005f5a4  mov     cs:qword_1400B5780, rax
0x14005f5ab  lea     rbx, SetCharOffsets
0x14005f5b2  mov     cs:qword_1400B5798, rax
0x14005f5b9  lea     r15, encoding
0x14005f5c0  lea     rax, qword_1400B57A8
0x14005f5c7  mov     cs:qword_1400B5738, r9
0x14005f5ce  mov     cs:FontDict, rax
0x14005f5d5  lea     rbp, aEncoding; "Encoding"
0x14005f5dc  lea     rax, accentEncoding
0x14005f5e3  mov     cs:dword_1400B70C8, 25h ; '%'
0x14005f5ed  mov     cs:qword_1400B57B8, rax
0x14005f5f4  lea     rax, aAccentencoding; "AccentEncoding"
0x14005f5fb  mov     cs:qword_1400B57A8, rax
  ... truncated ...
```
